## 写在最前
默认情况下，要打开一个页面，浏览器必须下载、解析和处理所有的外部样式表，然后才能在用户屏幕上显示或呈现内容。这样就必须从网络下载**每个**外部样式表，这些额外的网络行程会大大增加用户在屏幕上看到任何内容之前必须等待的时间。 
但是实际情况却是，一个比较大的样式表，往往关键css只占很小的一部分。 这篇文章就会介绍如何利用`critical`提取一个页面上的关键css以及推迟非关键css

1. 首先要安装`node.js` ,这里就不说说明了  很简单
2. 打开cmd命令， 输入命令 `npm i -D critical`  进行安装，安装完成以后，会在你目录 `C:\Users\{UserName}\AppData\Roaming\npm\node_modules` 创建一个critical文件夹。 `{UserName}`是你计算机的用户名

	> AppData可能是隐藏的目录
3. 在`C:\Users\{UserName}\AppData\Roaming\npm\node_modules\critical`目录下新建pcs.js文件，文件名自定义，文件内容如下：
 base是你的根目录
 src是你项目的html文件
 target下面的html是处理后的html文件，css是处理后css文件
	```javascript
	const critical = require('critical');
	critical.generate({
	  inline: true,
	  base: 'D:/love.github.io/AmJson/md5/',
	  src: 'md5.html',
	  target: {
	    html: 'index-critical.html',
	    css: 'critical.css',
	  },
	  width: 1300,
	  height: 900,
	});
	```
4. 在`C:\Users\{UserName}\AppData\Roaming\npm\node_modules\critical`目录下执行命令`node fileName.js`，会在你源文件的目录下生成html和css文件
	>fileName是你的文件名
5. 你可以打开`index-critical.html`这个文件看一下，主体代码都不会动， 他会把关键css直接内联，直接用`<style></style>`包裹起来，然后把你以前的外部css文件全部延迟加载， 你要做的就是引进`critical.css`就可以了
6. 现在再去测试一下你页面的加载速度，你会发现速度确实会快很多，如果你项目本身的css文件比较大，效果会比较显著
7. 更多的critical知识可以参考github  [https://github.com/addyosmani/critical/blob/master/README.md](https://github.com/addyosmani/critical/blob/master/README.md)
8. Chrome自带的Coverage也可以很直观的看到哪些是关键css，但是有一个缺点，就是没法导出，只能手动或者写代码处理，后续的文章会介绍

+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)
