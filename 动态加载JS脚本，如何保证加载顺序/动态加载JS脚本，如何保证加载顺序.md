## 写在最前
很多时候，我们需要动态加载javascript脚本， 尤其是在做网页优化的时候，需要保证的是最快的速度打开网页， 但是某几个JS文件其实并不是整个页面需要的脚本，可能只是某个功能需要的。 这样我们就可以在页面加载完成以后再加载它，这样就保证了页面的打开速度

1. 基本写法

```javascript
<script>
	window.addEventListener('load',
		function() {
			var jquery= document.createElement("script");
			jquery.type = "text/javascript";
			jquery.src = "/index/jquery.js";
			document.getElementsByTagName("head")[0].appendChild(jquery);
		
			var bootstrap = document.createElement("script");
			bootstrap.type = "text/javascript";
			bootstrap.src = "/index/bootstrap.js";
			document.getElementsByTagName("head")[0].appendChild(bootstrap);
	});
</script>
```
+ 如果对JS的加载顺序没有要求的话，这么写是没错的，你会发现在你网页加载完成以后，`jquery.js`和`bootstrap.js`才会加载，不会影响页面的加载速度

 但是如果对JS的加载顺序有要求，你会发现这样写就会有问题，他并不是按我们的书写顺序进行加载，随后我进行了很多次实验依然不行， 我只好试着去找了一下权威机构的一些官方文档， 终于让我发现了问题. 在MDN Web Doc对[MDN Javascript](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)的一段介绍中是这么说的
 

> To request script-inserted external scripts be executed in the insertion order in browsers where the document.createElement("script").async evaluates to true (such as Firefox 4), set async="false" on the scripts you want to maintain order.

对照翻译过来的意思就是：如果你使用`document.createElement（“ script”）`来动态的创建脚本，那么他的属性`async`为true，如果你想按顺序加载，请将其设置成false.    如果你还不了解`async`属性，也可以看我上面发的连接，里面有详细的介绍。  现在我们修改一下代码


```javascript
<script>
	window.addEventListener('load',
		function() {
			var jquery= document.createElement("script");
			jquery.type = "text/javascript";
			jquery.src = "/index/jquery.js";
			jquery.async = false;
			document.getElementsByTagName("head")[0].appendChild(jquery);
		
			var bootstrap = document.createElement("script");
			bootstrap.type = "text/javascript";
			bootstrap.src = "/index/bootstrap.js";
			bootstrap.async = false;
			document.getElementsByTagName("head")[0].appendChild(bootstrap);
	});
</script>
```
这样，JS就会按我们预想的顺序进行加载了


+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)