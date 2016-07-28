### WebView图片显示问题(微信相关)

最近接入微信目录式的图文列表，发现在三星手机上能够显示图片，但是华为和Vivo就是显示不了图片。网上找了不少资料，都只是说明要打开JS，但是打开依旧没有用。后面发现是webview 在使用HTTPS时有的图片不能加载，故搜索发现后，记录如下：

Android webview 从Lollipop开始webview默认不允许混合模式，https当中不能加载http资源，需要设置开启。

Mixed content using HTTP and HTTPS on WebViews are disabled by default starting Lollipop. Is possible that is not working on devices with Lollipop? If this is the case, you can change the default WebView setting on Lollipop using:

webSettings.setMixedContentMode(WebSettings.MIXED_CONTENT_ALWAYS_ALLOW);
Documentation here: [WebSettings API](http://developer.android.com/reference/android/webkit/WebSettings.html#setMixedContentMode(int))