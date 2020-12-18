2020-12-18 

   
 &emsp;自己的小网站(https://www.jsonformatting.com)已经做的差不多了，功能很少，这个网站主要还是还是想做一下SEO，我已经提交谷歌搜索半个月了，也被收录了，但是一直没有显示到Google的搜索结果中，有点着急不知道怎么回事， 前面自己的文章还说SEO是个慢工出细活的工作，没想到自己先着急了。  在网上查了一下资料，一方面是做自己网站的优化，更重要的一方面是要做大量外链和反链， 而我的网站是个新站点，自然没有什么外链了，我想问题可能就出自这，以此来以文章博客的形式，记录小网站的优化之路，希望我能坚持下去，也把我的一些经验分享给你们。 


 &emsp;首先说几个重要的点：
 
	 1. 去相关的维基百科建立词条，这个很重要，也有一定的难度，有的需要审核 非常严格
	 2. 活跃推特，facebook等社区
	 3. 找几个排名靠前的进行合作，更难了， 但是不试一试怎么知道不行呢
	 4. 找几篇写的好的博文（比如介绍JSON相关知识的，扩展知识的），copy下来，加入自己的理解

 &emsp;昨天的时候， 用谷歌账号关联登录了[afrefs](https://ahrefs.com/ "afrefs") ，这个网站对于站长来说必须是必备的，如果你想把SEO做的还不错的话。  功能非常强大，当然费用也很贵，不过也有免费的一些功能， 我准备先用免费功能优化一下自己的网站，效果好的话花钱买一个会员。

 &emsp;登陆以后关联自己的网站，然后他会自动对你的网站进行一个简单的评估，并把评估结果发到你的邮箱，我的结果
  ![网站问题](https://github.com/nalani5210/love.github.io/blob/bolg/SEO%E4%BC%98%E5%8C%96%E6%97%A5%E8%AE%B0/2020-12-18-afrefs%E5%AF%B9%E7%BD%91%E7%AB%99%E7%9A%84%E6%A3%80%E6%B5%8B%E7%BB%93%E6%9E%9C.png?raw=true "网站问题") 

 自认为不错的小网站，挺受打击的， 一个一个解决吧


   1 . <font color=red>Redirected page has no incoming internal links  （重定向页面没有传入的内部链接）</font>

&emsp;说实话一开始看到的时候，我有点懵，内部链接我知道，就是同域名下页面之间的跳转，我网站里页面之间的跳转都是用的绝对路径，在我想来，搜索引擎来抓取的时候，绝对路径有利于我内部网站链接的扩散。 然后我看了ahrefs对[SEO内部链接优化：实战指南](https://ahrefs.com/blog/zh/internal-links-for-seo/ "SEO内部链接优化：实战指南")的介绍，发现我还是太单纯了

改进：  我把网站内以前所有的跳转https://www.josnformatting.com/a /b /c都改成了/a /b /c，  然后重新提交 看看效果

   2 . <font color=red>Duplicate pages without canonical （重复的页面没有规范）</font>

&emsp; 这个我知道 ，我页面有很多重复页面，google收录的时候如果检测到不同页面有很多相同的元素，会判定为重复页面，这时你要告诉google哪个才是规范版本，不然很容易不收录。  这个我当时看到过，忙起来忘了改了.

[权威内容标签—简明入门指南](https://ahrefs.com/blog/zh/canonical-tags/ "权威内容标签—简明入门指南")

 
	在规范页面添加<link rel="canonical" href="https://www.xxxx.com/xxxx" />就可以


   3 . <font color=red>Page has no outgoing links （页面没有传出链接）</font>

&emsp; 这个也好理解，就是这个页面没有任何对内或者对外的连接，想跳出页面只能依靠后退类似的操作。 根据自己情况添加就可以

   4 . <font color=red>Meta description tag missing or empty （元描述标记缺失或为空）</font>

&emsp; 这个看英文比较好理解， Meta标签， description没写或者为空， 你点开会提示是哪几个页面， 我这是因为iframe嵌入的问题， 添加上就可以。

   5 . <font color=red>4XX page in sitemap  </font>

&emsp;你的sitemap文件里的路径有404的页面， 仔细检查一下！   图里那几个404都是这个原因， 其中一个页面的路径改了  我没有及时更新。

   6 . <font color=#FD8F17>Open Graph tags incomplete (打开图标签不完整) </font>

&emsp;每一页的四个必需的Open Graph标签og:title，og:type，og:image，和og:url。 少一个都会有警告 ，加上吧。

   7 . <font color=#FD8F17>3XX redirect </font>

   8 . <font color=red>Orphan page (has no incoming internal links) 孤立页面（没有传入的内部链接） </font>

&emsp; 网站的孤立页面没有传入的内部链接。  在其他页面配置下就可以 ， 我是因为嵌套页面所以没配置

   9 . <font color=#FD8F17>H1 tag missing or empty </font>


&emsp; 页面没有H1标签

  10 . 其他的我大概说一下，可能还有的我没碰到。

页面上meta标签的description，尽量多写一点，在搜索结果展示还是有一定作用

善用ahrefs的提示，它会告诉你错误或者警告如何修复，并且会给你相应的文章链接，有一些文章讲的非常细

今天网站的评分从82提到了100，还不错还不错


