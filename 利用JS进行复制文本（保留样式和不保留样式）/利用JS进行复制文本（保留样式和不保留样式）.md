## 这篇文章说一下怎么利用JS进行文本的复制

 1. 复制不保留样式 
```js
$('#copy').on('click', function (e) {
    const input = document.createElement('input');
    document.body.appendChild(input);
    input.setAttribute('value', "要复制的内容")
    input.select();
    if (document.execCommand('copy')) {
        console.log(document.execCommand('copy'));
    }
    document.body.removeChild(input);
});
```
 2. 复制保留样式 
```js
$('#copy').on('click', function (e) {
        const input = document.createElement('textarea');
        document.body.appendChild(input);
        input.value = $(".conter")[0].innerText;
        input.select();
        if (document.execCommand('copy')) {
            console.log(document.execCommand('copy'));
        }
        document.body.removeChild(input);
    });
});
```

要保留样式，需要用到 `textarea` 
`textarea` 赋值要这么写 `input.value = ‘要复制的内容’;`

如果你的js样式太乱，建议用 [js格式化](https://www.jsonformatting.com/js-beautifier/)先进行格式化再做操作

+ 我的网站: [https://www.jsonformatting.com/](https://www.jsonformatting.com/)
+ 我的思否: [https://segmentfault.com/u/json_formatter/articles](https://segmentfault.com/u/json_formatter/articles)