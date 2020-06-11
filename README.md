# ycrash-web，安卓崩溃异常捕获类Web端

用于展示ycrash安卓端提交的崩溃异常信息

前后端分离，这儿是纯HTML前端工程，要查看请求，请把本工程放入nginx的html文件夹中。

**配套安卓端异常捕获看过来：[点击前往](https://github.com/yutils/ycrash)**

**配套的Server端请看过来：[点击前往](https://github.com/yutils/ycrash-server)**

请把 proxy_pass 指向 server 端

<font color=#0099ff size=4 >nginx配置</font>
``` 
server {
        listen       52580;
        server_name  localhost;

        #首页
        location / {
          root  html;
          index login/index.html;
        }
 		
        #转发
        location /crash {
          proxy_pass   http://127.0.0.1:8090;
        }
 		
        #404错误
        error_page  404				/404.html;
        location = /404.html{
          root   html/error;
        }
 		
        #500错误
        error_page  500 502 503 504  /500.html;
        location = /500.html {
          root   html/error;
        }
}
```


Github地址：[https://github.com/yutils/ycrash-server](https://github.com/yutils/ycrash-server)

我的CSDN：[https://blog.csdn.net/Yu1441](https://blog.csdn.net/Yu1441)

感谢关注微博：[细雨若静](https://weibo.com/32005200)
