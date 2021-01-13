HTTP2已经发布很久了，HTTP2相比于1.0有了很大的提升，在语义兼容1.0的前提下，大幅度的提升了web性能，进一步减少了网络延迟。
查看你的浏览器是否支持HTTP2，并且对比1.0与2.0的性能差距 [http2.0](https://http2.akamai.com/demo  "http2.0") 

正好最近在对网站进行检测的时候，被告知建议使用HTTP2协议，查找了一番资料以后配置成功，现在分享一下过程

##安装前提
> 1 nginx版本必须在 1.9.5之后.    [nginx官方解释](https://www.nginx.com/blog/nginx-1-9-5/  "nginx官方解释")  
> 2 只支持https协议的网站， 怎么配置https? 见我另一篇博客文章 [配置https](https://nalani52.blogspot.com/2020/12/windowsnginxssllets-encrypt.html  "配置https")   

##配置nginx


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

##验证
打开网站(可能需要翻墙)[http2.0验证](https://tools.keycdn.com/http2-test/  "http2.0验证")  验证你的网站是不是已经支持2.0协议了
