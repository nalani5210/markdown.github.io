#写在最前
现如今，百度、谷歌、Github等网站已经全站启用https，https就像是给网站上了一个“锁”，HTTPS做的就是给请求加密，让其对用户更加安全。对于自身而言除了保障用户利益外，还可避免本属于自己的流量被挟持。谷歌已经将http定义为不安全的网站，在我看来HTTPS已经是未来的趋势。

>1. 部署环境为Winodws Nginx
>2. Let's Encrypt是国外一个公共的免费SSL项目，由 Linux 基金会托管，由Mozilla、思科、Akamai、IdenTrust和EFF等组织发起！
>3. Let's Encrypt证书有效期三个月，每三个月需要续签证书 
>4. 利用win-acme工具来生成Let's Encrypt证书
>


1. 首先先在github上下载最新版的win-acme. <a href="https://github.com/win-acme/win-acme/releases/" title="点击下载" target="_blank">下载win-acme</a> 我下载的是win-acme.v2.1.12.943.x86.pluggable.zip这个版本
2.  下载nginx <a href="http://nginx.org/en/download.html" title="点击下载" target="_blank">下载nginx</a> 
3.  解压缩win-acme压缩包，打开wacs.exe ， 多图预警！
![第一步创建证书](https://image-static.segmentfault.com/251/185/2511859186-601663161c7c0)

![第二步 手动输入](https://image-static.segmentfault.com/126/928/1269289797-6016633ab8557)

![第三步 输入域名](https://image-static.segmentfault.com/202/042/2020420199-60166360473ef)

![第四步 直接回车](https://image-static.segmentfault.com/131/572/1315723123-601663817fac9)

![第五步 选择dns验证域名](https://image-static.segmentfault.com/351/494/3514940924-6016639fc230b)

![第六步 RSA](https://image-static.segmentfault.com/383/458/3834586549-601663bf87689)

![第七步  选nginx支持](https://image-static.segmentfault.com/117/163/1171635882-601663dad0efe)

![第八步 秘钥存放位置](https://image-static.segmentfault.com/288/269/2882692270-601663faf2a4d)

![第九步 过](https://image-static.segmentfault.com/375/531/3755313207-6016641675c56)

![第十步 过](https://image-static.segmentfault.com/243/076/243076098-6016642f9e23b)

![第十一步 域名解析1](https://image-static.segmentfault.com/366/511/366511961-6016644d43aa5)

![第十二步 域名解析2](https://image-static.segmentfault.com/247/895/2478956586-6016646a854f5)

![第十三步  验证成功](https://image-static.segmentfault.com/270/603/2706037626-60166489c3b2b)

![第十四步 查看本地文件](https://image-static.segmentfault.com/363/657/363657230-601664a4958f4)



配置nginx ， 打开/conf/nginx.conf
```
server {
    listen       443 ssl;
    server_name  你的域名;

    ssl_certificate      D:/nginx-1.15.6/ssl/xxxxx-chain.pem;  
    ssl_certificate_key  D:/nginx-1.15.6/ssl/xxxxxx-key.pem;  

    ssl_session_timeout 5m;
    charset utf-8;

    location / {
        root  D:/index/;
        index index.html;
    }
}
```

启动nginx，访问域名！

证书的有效期是90天，到期前需要续上，研究一下怎么续期及自动续期，到时候会分享出来

同一域名、规定时间内申请证书是有限制的， 具体见官方介绍 <a href="https://letsencrypt.org/docs/rate-limits/" title="点击查看申请限制" target="_blank">申请限制</a>

+ 我的网站 [https://www.jsonformatting.com/](https://www.jsonformatting.com/)