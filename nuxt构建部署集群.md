### nuxt项目开发完成后，要做部署

#### 本地 npm run build 构建出来的，.nuxt目录+static目录+nuxt.config.js+package.json拷贝到对应的服务器
#### 服务器 npm install
#### npm run start 启动服务；

``` bash
  之前是将所有文件都从集测拷贝到正式环境；发现没有必要
```

### 如何使用cdn部署静态资源

#### nuxt build出来的静态资源包含在 .nuxt/dist/client下面，也就是将此目录的资源进行cdn部署；

#### 需要注意的是，使用cdn的话，需要nuxt.config.js 做配置，具体如下 

``` bash
参考：https://zh.nuxtjs.org/api/configuration-build/#publicpath

Nuxt.js允许您将dist文件上传到CDN来获得最快渲染性能，只需将publicPath设置为CDN即可

  build: {
    publicPath: 'https://cdn.nuxtjs.org'
  }


当启动nuxt build时， 将.nuxt/dist/client目录的内容上传到您的CDN即可！

```