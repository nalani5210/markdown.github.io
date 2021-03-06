最近做了一个在线服务类的小网站，为了能在google上有好的排名，自己做了一些相关的优化。
相关的优化方案网上应该都可以找到，我自己做了一些整理。

**代码结构**
首先说一下网站的， 是table结构还是div
a. 如果是div+css结构，是比较适合做SEO的，网页内容和网页样式尽量分开书写，分开管理，这是属于精简的代码结构；
b. 如果是table结构，很容易产生冗余代码，属于不精简的代码结构，不适合做SEO，可能需要重新建站，这就可能比较麻烦了。
我的网站是div结构的，我也在google观察了一些排名比较靠前的网站，确实没见到用table结构的。

**信噪比**
信噪比指的是网页有效信息和无效信息的比例；
有效信息是文字
无效信息指的是无效代码、空代码、富媒体；富媒体指的是视频、音频，flash动画、JavaScript。
这其实是平时编码的一个好习惯，文字不要有错别字，无效的信息要及时清理。

**iframe**
iframe是一个比较特殊的标签。被iframe嵌套的内容不会被搜索引擎抓取，一般用于出站链接的广告位。
但是项目有一些情况需要用到iframe，比如嵌套一个页面，而且我们有希望这个被嵌套的页面被搜索引擎抓取，我自己的替代方案是用object标签。

**javascript**
js有一个特点，js输出的内容搜索引擎不识别。所以页面的关键字千万不要用js来做输出！
还有网页在使用js时尽量放置在网页底部，尽量不影响搜索引擎抓取常规内容。
这里再补充几点js的，是后面找SEO相关资料发现的

> 绝对避免导航及其他链接使用JavaScript. 导航和链接是搜索引擎抓取网页的赖以生存之本，如果搜索引擎无法抓取网页，则代表了网页不会出现在索引结果中，也就无从谈起排名了
> 
> 尽量避免对内容使用JavaScript。尤其是与关键词相关部分的内容，应该尽量避免使用JavaScript来展现，否则毫无疑问是要降低关键词密度的
> 
> 实在需要使用JavaScript的部分，将这部分JavaScript脚本放在一个或几个.js文件中，这样能够避免干扰到搜索引擎的抓取和分析
> 
> 实在不能放在.js文件中的部分JavaScript脚本，将它们放在html代码的底端，之前，这样使搜索引擎分析网页时最后才会发现它，降低对搜索引擎的干扰

**h1-h6标签**
h1标记一个网页只能出现一次，整站所有页面h1需要对应同一个核心关键词，强调关键词[使用太多被搜索引擎处罚就得不值得了]，
这个很重要，把最重要的关键字用h1包起来 ！
h2-h3标记可以多次使用，尽量也不要太多；h4-h6可以不使用，基本没什么权重了。

**img和a标签**
img标记的alt属性，搜索引擎依靠图片alt属性来判断图片内容，文章中图片alt属性使用文章标题即可；
a标签的title属性，对于网页中非常重要的链接采用TITLE说明，有助于帮助搜索引擎找到网页的重点URL。

**display: none**
display:none对SEO的影响，网上的说法众说纷纭，所以我在自己的网站里，还是彻底抛弃了这种方法。我的替代方案有两种

```
.hiddenClass {
    width:1px;
    height:0;
    overflow:hidden;
 }
```

或者用z-index建立层叠关系，不过z-index需要提醒一点

> z-index 仅能在定位元素上奏效,即该元素不是默认的position:static
> 需要设置 position:absolute \| relative \| fixed;

**robots.txt**

a. 什么是 robots.txt 文件?

> robots.txt 文件规定了搜索引擎抓取工具可以/无法请求抓取您网站上的哪些网页或文件;
> 此文件主要用于使您的网站避免收到过多请求

b. 格式和位置规则

> 文件必须命名为 robots.txt
> 网站只能有1个 robots.txt 文件
> robots.txt 文件必须位于要应用到的网站主机的根目录下

c. robots.txt 文件中可以使用下列指令

+User-agent [必需，每个组需含一个或多个 User-agent 条目]
此规则的适用搜索引擎漫游器（即网页抓取工具软件）的名称。这是每条规则的首行内容。
支持通配符\*

> 几个比较常用的代理
> 
> 
> 1. Google: Googlebot
> 2. Google Images: Googlebot-Image
> 3. Bing: Bingbot
> 4. Yahoo: Slurp
> 5. Baidu: Baiduspider
> 6. DuckDuckGo:DuckDuckBot

```
示例 1：仅屏蔽 Googlebot
User-agent: Googlebot
Disallow: /

# 示例 2：屏蔽 Googlebot 和 Adsbot
User-agent: Googlebot
User-agent: AdsBot-Google
Disallow: /
```

* Disallow [每条规则需含至少一个或多个 Disallow 或 Allow 条目]
用户代理不应抓取的目录或网页（相对于根网域而言）。如果要指定网页，应提供浏览器中显示的完整网页名称；如果要指定目录，则应以标记/结尾。支持使用通配符\*表示路径前缀、后缀或整个字符串
* Allow [每条规则需含至少一个或多个 Disallow 或 Allow 条目]
上文中提到的用户代理应抓取的目录或网页（相对于根网域而言）。此指令用于替换Disallow指令，从而允许抓取已禁止访问的目录中的子目录或网页。如果要指定网页，就应提供浏览器中显示的完整网页名称；如果要指定目录，则应以标记/结尾。支持使用通配符\*表示路径前缀、后缀或整个字符串

```
示例 1 ：允许所有的机器人
        User-agent: *
        Allow:/
```

```
示例 2 ：仅允许特定的机器人：（name_spider用真实名字代替）
        User-agent: name_spider
        Allow:
```

```
示例 3 ：拦截所有的机器人
        User-agent: *
        Disallow: /
```

**Meta标签**
Meta标签的优化（以前是搜索引擎优化的重要手法，现在不是关键因素，但仍不可忽略不急） 主要是：Meta description、Meta keywords的设置。关键字密度要适中，也就是说你的关键字必须在页面中出现若干次。

**版权部分**
版权部分加上网站名称和链接或是强调一些关键词是很有必要，有总比没有强。

**支持移动端**
这点可能对比较大的网站有些不友好，而且有一些网站只是针对PC端，还有必要做移动端的适配吗？ 看看google怎么说的

> 移动设备正在改变世界。当今时代，智能手机几乎人手一部，大家都不停地用它与外界交流以及查找信息。在许多国家/地区，智能手机的数量已超过个人计算机的数量，因此拥有适合移动设备的网站已成为提升在线影响力的重要因素。

*如果您的网站尚不适合在移动设备上浏览，您应立即采取行动*
并且google有专门针对移动设备适应性测试的网站[移动设备适应性](https://search.google.com/test/mobile-friendly) , 可见对移动设备适配的重要性 。
附上google的官方说明 [https://developers.google.com/search/mobile-sites](https://developers.google.com/search/mobile-sites)


**外链**
外链的数量，对排名有**很大**的影响。

> 这段话是这篇文章存为草稿很长时间又添加上的. 外链的数量和质量，真的对权重有很大的影响，有句话说 内容为王外链为皇. 外链的建设真的太有必要了，后面还会有文章介绍外链的相关建设

**工具**
google官方提供了很多工具，非常方便

<a href="https://search.google.com/test/mobile-friendly" target="_blank">网页适应性测试</a>

[请求 Google 重新抓取您的网址](https://developers.google.com/search/docs/advanced/crawling/ask-google-to-recrawl)

[robots.txt测试工具](https://support.google.com/webmasters/answer/6062598)

<a href="https://validator.w3.org/" target="_blank">W3C HTML验证</a>

[衡量网站在Google搜索中的表现](https://developers.google.com/search/docs/basics/measure-performance-on-google/)

总之，SEO是个慢工细活的工程，不要指望三两天就能看到效果，每一点小小的改动都有可能影响你网站的权重（比如列举出来的，支持移动端\~）。

我的网站建站大概两个月左右了，现在某些关键字排名能在第五页前后，还是差了不少，最近也一直在做外链的建设

* 我的网站 [https://www.jsonformatting.com/](https://www.jsonformatting.com/)