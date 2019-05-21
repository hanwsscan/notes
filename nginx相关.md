# nginx相关问题及解决方式

## 启动进程里不显示，启动错误

``` bash
C:\nginx-1.11.4>nginx.exe

nginx: [emerg] invalid number of arguments in "proxy_pass" directive in C:\nginx-1.11.4/conf/nginx.conf:56

```

##### 原因，proxy_pass 缺少 ; 号 

``` bash
proxy_pass http://182.92.245.49:80;

```
