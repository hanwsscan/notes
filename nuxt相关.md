### nuxt 环境变量，根据环境变量配置接口地址并使用


#### package.json的script里配置 inte测试 prod正式
``` bash
"scripts": {
    "dev": "cross-env process.env.__ENV=inte nuxt",
    "devProd": "cross-env process.env.__ENV=prod nuxt",
    "build": "cross-env process.env.__ENV=prod nuxt build",
    "start": "cross-env process.env.__ENV=prod nuxt start"
  },
```

#### 根据 npm run xxx 读取环境变量
``` bash
// 初始化环境接口
if (process.env.__ENV == 'inte') {
  // console.log(process.env)
  process.env = {
    testLoginUrl: '//inte-cia.chanapp.chanjet.com/internal_api/authorizeByJsonp?client_id=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX',
    regsiterUrl: '//inte-register.chanjet.com/register?app=loan&callback=',
    regsiter4wapUrl: '//inte-register.chanjet.com/wap/register.html?app=loan&callback=',
    chanjetLoginJs: '//inte-passport.chanjet.com/js/modules/ChanjetLogin.js'
  }
  // console.log("process.env.__ENV 集测环境：" + process.env.__ENV)

} else if (process.env.__ENV == 'prod') {
  // console.log("正式环境")
  process.env = {
    testLoginUrl: '//cia.chanapp.chanjet.com/internal_api/authorizeByJsonp?client_id=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXX',
    regsiterUrl: '//register.chanjet.com/register?app=loan&callback=',
    regsiter4wapUrl: '//register.chanjet.com/wap/register.html?app=loan&callback=',
    chanjetLoginJs: '//passport.chanjet.com/js/modules/ChanjetLogin.js'
  }
  // console.log("process.env.__ENV 正式环境：" + process.env.__ENV)
} else {
  // console.log("其它环境")
}
```


#### 使用环境变量

##### $.getScript 加载第三方js，在function里调方法，否则会出现js未加载，文件里的方法报错，

``` bash
    //加载 process.env.chanjetLoginJs
    $.getScript(process.env.chanjetLoginJs, function () {
      var Clogin = ChanjetLogin.getInstance(params);
      Clogin.show();
    })

```

#### jenkins打包集测环境，正是环境是将集测打的包直接拷贝到正式环境，那么问题是，包可以直接拷过去，但是否可以执行 package.json里配置的不同的脚本

``` bash
    //本地开发
    "dev": "cross-env process.env.__ENV=inte nuxt",
    "devProd": "cross-env process.env.__ENV=prod nuxt",
    //构建集测
    "buildInte": "cross-env process.env.__ENV=inte nuxt build",
    "startInte": "cross-env process.env.__ENV=inte nuxt start",
    //集测环境的包考过来，但正式环境执行的是下面两条命令
    "buildProd": "cross-env process.env.__ENV=prod nuxt build",
    "startProd": "cross-env process.env.__ENV=prod nuxt start"
```
#### jenkins打包集测环境，正是环境是将集测打的包直接拷贝到正式环境，目前公司不支持正式环境build，所以无法采用上述方式；

### 最终解决方式：后端提供个 getEVN 接口，来取环境变量，根据接口返回，在配置不同的第三方接口调用；


