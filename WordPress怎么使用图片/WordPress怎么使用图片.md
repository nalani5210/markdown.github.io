## 标题
在使用wp写博客的时候，经常会用到图片，但是wp对本地图片的支持不是很好，这里作者用的方法是把图片上传到github，然后再用网络地址。

1. GitHub
首先，如果你没用过GitHub，那你要先了解GitHub是什么。
> GitHub 是一个面向开源及私有软件项目的托管平台，因为只支持 Git 作为唯一的版本库格式进行托管，故名 GitHub。
> 
简单来说，GitHub是一个开源的托管平台，可供自己或者其他人一起分享使用的一个平台。 先登录<a href="https://github.com/" title="GitHub官网" target="_blank">GitHub</a>，没有账号的先进行注册。 <strong>如果登录不了应该是限制网络的关系

![github新建repo](https://img-blog.csdnimg.cn/20210201164159312.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70)
![github新建repo2](https://img-blog.csdnimg.cn/20210201164159229.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70)

2. GitHubDesktop
为了更方便也为了很多没接触过github的人来说，用git的桌面工具更来的事半功倍。 不用命令行，直接操作就可以. <a href="https://desktop.github.com/" title="GitHubDesktop" target="_blank">点击下载</a>  下载完成直接安装

![关联Github进行登录](https://img-blog.csdnimg.cn/20210201164721528.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
点击Sign in to GitHub.com进行关联登录

![关联以后可以看到自己的repository](https://img-blog.csdnimg.cn/20210201164804678.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
选择要关联的仓库，进入主页面。 点击左上角菜单 File-Clone Repository 弹出对话框

![选择仓库下载到本地](https://img-blog.csdnimg.cn/2021020116484256.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
然后打开本地文件夹

![把图片文件件或者文件放到目录下](https://img-blog.csdnimg.cn/20210201164915194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
![commit](https://img-blog.csdnimg.cn/20210201164939840.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
![push](https://img-blog.csdnimg.cn/20210201164959982.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
![可以在git上看到已经上传的图片](https://img-blog.csdnimg.cn/20210201165025194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)
右键复制图片地址，就可以使用图片在wp了

![pull](https://img-blog.csdnimg.cn/20210201165054113.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2NzZGVyX3hq,size_16,color_FFFFFF,t_70#pic_center)

+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)