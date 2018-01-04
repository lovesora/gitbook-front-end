```js
// 判断图片是否加载完成
new function() {
    setTimeout(() => $('img')[0].complete && initAppAnimation() || arguments.callee(), 100);
}
```
