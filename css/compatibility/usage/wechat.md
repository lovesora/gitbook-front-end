# 微信内核
* 内核
> iOS微信`6.5.3`版本开始支持开发者手动切换`WKWebview`和`UIWebview`，使开发者可提前对`WKWebview`进行适配。

* 页面如何判断当前使用的`WKWebView`内核：
> 在页面中可通过微信注入的`window.__wxjs_is_wkwebview`变量判断当前使用的webview内核。 iOS微信6.5.3及其之后的版本 `window.__wxjs_is_wkwebview`为`true`时是使用`WKWebview`，为`false`或者 `undefine`时是`UIWebview` 。

* 适配
> 切换为`WKWebview`后，微信中的`WKWebview`行为和`Safari`中保持高度一致，唯一的区别是微信`WKWebview`中会注入微信`JSBridge`相关的脚本。

# Resources
* [微信iOS WKWebview 网页开发适配指南](http://www.infocool.net/kb/IOS/201701/266463.html)