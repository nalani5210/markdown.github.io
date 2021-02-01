互联网时代的来临，信息的交流非常重要，优秀的信息共享平台越来越多，其中个人博客就是一种非常受欢迎的方式。 这里介绍一下github+Hexo的方式，如果你也想搭建自己的个人博客，可以跟着教程快速搭建一个属于自己的博客吧。

> 什么是Hexo?
> Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

1. 安装git
打开 <a href="https://git-scm.com/downloads" title="git官网" target="_blank">git官网</a> ，选择自己电脑系统，然后选对应版本的安装包进行安装，然后一路进行傻瓜式的安装就好。如果安装成功，桌面鼠标右键会有git的菜单
![git安装成功](https://image-static.segmentfault.com/413/681/4136815201-601379407a248)
2. 安装node.js
如果是win10系统， <a href="https://nodejs.org/en/download/" title="打开node官网" target="_blank">打开node官网</a> 直接下载最新的版本就行，别下错版本；
如果是win7系统，可能不支持最新版本， <a href="https://nodejs.org/dist/v12.18.3/" title="点这下载" target="_blank">点这下载</a> ， 我都是下msi文件，直接安装完事 很方便。 安装完成以后，win+R打开cmd，输入node，有提示就代表安装成功了。 <strong>node.js版本不能低于12</strong>
![node安装成功](https://image-static.segmentfault.com/670/226/670226780-601379e82f6c5)

3. 安装Hexo

(1)首先修改 npm 的安装源，如果不换安装的时候会非常慢，这里换成淘宝的npm镜像
> $ npm config set registry https://registry.npm.taobao.org

(2)安装Hexo
> $ npm install -g hexo-cli

(3)定位到你本地的hexo文件夹(你自己创建的文件夹，任何路径任何名字都可以，最好别有中文),
> $ cd /d D:\Hexo    
 
(4)创建主文件夹 （速度可能有点慢，如果换了源时间还特别长，看看是不是github卡住了，挂一个代理试试），这个文件夹就是以后放代码的地方，建议别乱放
> $ hexo init bolg  
 
如果这一步卡住了，那就追加一个npm的安装源
>$ npm --registry https://registry.npm.taobao.org info underscore

(5)生成网站静态文件 （默认设置public文件夹）
> $ hexo g

(6)启动服务
> $ hexo s

打开浏览器访问 http://localhost:4000就能看到内容。默认的官方主题，可能会比较丑

+ 我的网站 [https://www.jsonformatting.com/](https://www.jsonformatting.com/)