## 写在最前
很多时候，网站为了提高访问速度，往往从细节开始做起，我在优化自己网站的时候，就会把生产环境的html文件进行压缩。 现在网站有很多在线的功能，但是项目内的html文件往往很多，不可能一个一个来，看了google官方的一些资料，可以用`gulp`进行批量压缩
## 安装
 1. 首先要安装`node.js` ,这里就不说说明了  很简单
 2. 安装`gulp`  , 打开cmd，输入命令  `npm install gulp-cli -g` ， 安装完成以后，会在你目录 `C:\Users\{UserName}\AppData\Roaming\npm\node_modules` 创建一个gulp-cli文件夹。 `{UserName}`是你计算机的用户名
	> AppData可能是隐藏的目录

 4. 安装 `gulp-html-minifier` ，  打开cmd，输入命令  `npm install gulp-html-minifier`
 5. 在`C:\Users\{UserName}\AppData\Roaming\npm\node_modules\gulp-cli`目录下新建gulpfile.js文件，文件内容如下.
src根据实际情况替换
```c
var gulp = require('gulp');
var htmlmin = require('gulp-html-minifier');
gulp.task('minify', function() {
  gulp.src('D:/json/*/*.html') //development location
    .pipe(htmlmin({collapseWhitespace: true}))
    .pipe(gulp.dest('./dist')) //deployment location
});
```
 5. 在`C:\Users\{UserName}\AppData\Roaming\npm\node_modules\gulp-cli`目录执行命令`gulp minify`
 6. 查看生成的文件夹`dist`文件夹内，已经压缩好的html文件
 7. 如果开发需要格式化，可以用 [html格式化](https://www.jsonformatting.com/html-formatter/)


+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)