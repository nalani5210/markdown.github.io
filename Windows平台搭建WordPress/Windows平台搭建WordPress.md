 

## 写在最前

 如果你想建立自己的博客，又不想受制于第三方平台的限制，那么自建博客就是你最好的选择。这里推荐使用WordPress进行建站
 
 
 > 建站基本步骤
 > 1. 域名
 > 2. 服务器
 > 3. 安装xampp
 > 4. 安装wordpress
 > 5. 域名解析

 1. 域名
     
首先，如果你希望你的博客对外开放，与大家一起交流，那么域名是必须的； 如果你建立博客只是想自己看不希望对外开放，那么域名是不需要的。
域名的购买方式有很多，我习惯去万网 <a href="https://wanwang.aliyun.com/domain/searchresult#/?keyword=&amp;suffix=com" title="万网" target="_blank">万网购买域名</a> 。直接搜索喜欢的域名直接购买，域名的选择没有要求，建议买便宜的就行 ，够用！</p>

2. 服务器

同样，如果博客不希望对外，服务器同样不用买，用自己的主机就可以. 服务器我推荐几种方式：
a. 谷歌服务器
前提是需要翻墙。 登录  <a href="https://www.google.com.hk/" title="google" target="_blank">google</a>，注册账号，这里具体的注册流程就不细讲了。 有了账号以后登录<a href="https://cloud.google.com/?hl=zh-cN" title="谷歌云" target="_blank">谷歌云计算服务</a> ，点击免费试用，按照步骤来填就可以，谷歌会免费送你 $300 赠金用来购买服务器并且未来90天内都是免费。这里需要注意一点，<strong>需要个人有一张双币（或者全币种）的信用卡才可以</strong>。

b. AWS
前提同样需要翻墙。 登录  <a href="https://aws.amazon.com/cn/" title="AWS" target="_blank">aws.amazon官网</a>，注册账号。 <strong>同样需要个人有一张双币（或者全币种）的信用卡才可以</strong>。 不细讲了，我会单独开一文章来说 。AWS免费12个月

c. 阿里云/腾讯云/华为云等等
国内的云服务厂家众多，可以挑选一家或者等活动购买，配置的话用基础配置就可以，如果后期不够再加。

3. 安装xampp
> xampp是什么?
>  xampp是一个把Apache网页服务器与PHP、Mysql等集合在一起的安装包，允许用户可以在个人的电脑上或者服务器轻易的建立网页服务器。
  
<a href="https://www.apachefriends.org/index.html" title="xampp下载" target="_blank">点击下载xampp</a>
一直next，安装好以后打开目录，xampp-control.exe 就是我们以后的启动程序了
![安装xmapp](https://img-blog.csdnimg.cn/20210128165932985.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
如果一切没问题，那么xampp就已经安装好了

4. 安装WordPress
 
<a href="https://cn.wordpress.org/wordpress-4.9.4-zh_CN.zip" title="WordPress下载" target="_blank">点击下载WordPress</a> 下载完以后，压缩，将所有文件放在`\xampp\htdocs`目录下
![wp文件放在指定目录](https://img-blog.csdnimg.cn/20210128170408699.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)

打开浏览器输入127.0.0.1:80，如果前面都没问题，会跳转到绑定数据库安装程序的页面，<strong>先别忙着点击开始</strong>，我们先切回到xampp程序。

![建立数据库](https://img-blog.csdnimg.cn/20210128170520116.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
打开`\xampp\htdocs\`目录下的wp-config-sample.php文件，推荐使用<a href="https://notepad-plus-plus.org/downloads/" title="notepad++下载" target="_blank">notepad++</a>编辑器

![wp-config-sample文件修改](https://img-blog.csdnimg.cn/20210128170605232.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
设置好以后，切回浏览器，点击开始安装。 填上对应的数据库信息 及 后续的站点基本信息。 浏览器输入127.0.0.1  就可以打开个人的博客地址了

5. 解析

这里拿阿里云的做说明，登录到后台，对应的域名点[解析]

![解析1](https://img-blog.csdnimg.cn/20210128170759127.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70)
![解析2](https://img-blog.csdnimg.cn/2021012817075997.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70)

+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)