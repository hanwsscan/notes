### nuxt项目开发完成后，要做部署，结合jenkins构建出来的包；

#### jenkins构建的包，包含
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