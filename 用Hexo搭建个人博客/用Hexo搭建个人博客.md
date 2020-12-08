**写在最前**

   互联网时代的来临，信息的交流非常重要，优秀的信息共享平台越来越多，其中个人博客就是一种非常受欢迎的方式。 这里介绍一下github+Hexo的方式，如果你也想搭建自己的个人博客，可以跟着教程快速搭建一个属于自己的博客吧。

**Hexo**

	Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

**安装前提**

- 安装git
- 安装nodejs

<font face="微软雅黑" size=5>开始安装</font>

* **安装git**     
打开 [git官网](https://git-scm.com/downloads  "git官网") ，选择自己电脑系统，然后选对应版本的安装包进行安装，然后一路进行傻瓜式的安装就好。如果安装成功，桌面鼠标右键会有git的菜单
 ![git安装成功](https://github.com/nalani5210/love.github.io/blob/bolg/%E7%94%A8Hexo%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/git%E5%AE%89%E8%A3%85%E6%88%90%E5%8A%9F.png?raw=true "git安装成功")

* **安装node.js**     
 如果是win10系统， [打开node官网](https://nodejs.org/en/download/  "打开node官网") 直接下载最新的版本就行，别下错版本；   
如果是win7系统，可能不支持最新版本， [点这下载](https://nodejs.org/dist/v12.18.3/    "点这下载") ， 我都是下msi文件，直接安装完事 很方便。 安装完成以后，win+R打开cmd，输入node，有提示就代表安装成功了。 **node.js版本不能低于12**   
![node安装成功](https://github.com/nalani5210/love.github.io/blob/bolg/%E7%94%A8Hexo%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/node%E5%AE%89%E8%A3%85%E6%88%90%E5%8A%9F.png?raw=true "node安装成功")


* **安装Hexo**    
1.首先修改 npm 的安装源，如果不换安装的时候会非常慢，这里换成淘宝的NPM镜像。

		$ npm config set registry https://registry.npm.taobao.org
2.安装Hexo

		$ npm install -g hexo-cli
3.定位到你本地的hexo文件夹(你自己创建的文件夹，任何路径任何名字都可以，最好别有中文),然后npm源再切换一下淘宝（切换源这一步可以在任意目录执行）

		$ cd /d D:\Hexo
		$ npm --registry https://registry.npm.taobao.org info underscore
3.创建博客主文件夹 （速度可能有点慢，如果换了源时间还特别长，看看是不是github卡住了，挂一个代理试试）

		$ hexo init bolg