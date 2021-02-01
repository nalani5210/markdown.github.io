在做网站的时候，网站的某些url地址一般都会因为某些原因进行变动，这时候如果网站已经做了很多外链，就需要利用301重定向进行转发.

先大概总结一下网站url地址变动的原因

> 1. 更好更直观的url地址更利用SEO(我就是因为这个原因)
> 2. 网站目录发生变化
> 3. 旧地址存在问题，比如过滤词之类
> 4. http转https

那么何时才适合使用301呢？
> 1. 永久更改网页的URL
> 2. 永久迁移到新域名
> 3. 从HTTP切换到HTTPS

1. http转https

> 为什么要使用https?
> 1. Google 已调整搜索引擎算法，让采用 HTTPS 的网站在搜索中排名更靠前
> 2. 从 2017 年开始，Chrome 浏览器已把采用 HTTP 协议的网站标记为不安全网站
> 3. 新一代的 HTTP/2 协议的支持需以 HTTPS 为基础
> 4. 更安全，而且是趋势

nginx配置
```
server {
  listen 80;
  server_name example.com www.example.com;
  return 301 https://www.example.com$request_uri;
}
```

2. 普通url地址变动
举个例子， 地址由/abc改成/qwe , nginx只需要这么配置
```
location ^~ /abc {
	rewrite ^/abc(.*)$ /qwe/$1 permanent;
}
```

+ 我的网站  [https://www.jsonformatting.com/](https://www.jsonformatting.com/)