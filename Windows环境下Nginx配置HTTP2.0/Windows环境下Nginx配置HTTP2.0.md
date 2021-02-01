HTTP2已经发布很久了，HTTP2相比于1.0有了很大的提升，在语义兼容1.0的前提下，大幅度的提升了web性能，进一步减少了网络延迟。
查看你的浏览器是否支持HTTP2，并且对比1.0与2.0的性能差距 <a href="https://http2.akamai.com/demo" title="http2.0">http2.0</a> 

正好最近在对网站进行检测的时候，被告知建议使用HTTP2协议，查找了一番资料以后配置成功，现在分享一下过程

> 1 nginx版本必须在 1.9.5之后.    <a href="https://www.nginx.com/blog/nginx-1-9-5/" title="nginx官方解释">nginx官方解释</a>
> 2 只支持https协议的网站， 怎么配置https? 见我另一篇博客文章 <a href="https://segmentfault.com/a/1190000039135687" title="配置https">配置https</a>  
> 

配置nginx

```
server {
    listen       443 ssl http2 default_server;
    server_name  你的域名;

    ssl_certificate      D:/nginx-1.15.6/ssl/xxxxx-chain.pem;  #你的证书
    ssl_certificate_key  D:/nginx-1.15.6/ssl/xxxxxx-key.pem;   #你的证书

    ssl_session_timeout 5m;
    charset utf-8;

    location / {
        root  D:/index/;
        index index.html;
    }
}
```

验证

打开网站 <a href="https://tools.keycdn.com/http2-test/" title="http2.0验证">http2.0验证</a>  验证你的网站是不是已经支持2.0协议了

+ 我的网站 [https://www.jsonformatting.com/](https://www.jsonformatting.com/)