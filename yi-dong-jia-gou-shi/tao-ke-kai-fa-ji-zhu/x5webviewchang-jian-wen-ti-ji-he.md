# x5WebView常见问题集合

### 最近有不少人反馈打开APP启动页的时候显示加载中 加载到70-80%就动不了
解决办法：网页页面部分资源加载未完成
参考文档：[解决华为等手机浏览器不兼容vue框架的问题](https://www.jianshu.com/p/407fe17cc0ed)

### 解决WebView写入localstorage但首次加载取不到值的问题
原因：token注入是在页面加载完毕之后进行，而页面加载完毕，页面中的js也就基本执行完毕了，所以页面中原有的js执行获取token是获取不到的。
解决方法：在h5内判断token是否为空，如果是则重新刷新页面。因为token为空是在首次加载页面时发生的，所以也只有在首次加载页面时会重新刷新，只有首次加载页面成功，写入localstorage，后面获取localstorage都不会失败了。

参考文档：[解决WebView写入localstorage但首次加载取不到值的问题
](https://www.jianshu.com/p/a6c2496467a3)
