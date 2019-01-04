# JYWKWebViewJavascriptBridge
JYWKWebViewJavascriptBridge

此项目拷贝于： https://github.com/jiyifanzi/JYWKWebViewJavascriptBridge
修复内存泄露问题。

请注意，非本人代码，如果使用，pod 'JYWKWebViewJavascriptBridge' ，使用的是原作者代码。

- (void)dealloc {
    [self removeScriptMessageHandlers];
}

如果将生命周期关联至于WKWebView，那么需要在WKWebView 前释放。

如 webView.bridge = [[JYWKWebViewJavascriptBridge alloc] initWithWebView:webView]; bridge定义为strong，那么可以在UIViewController的dealloc中调用 self.webView.bridge = nil 将bridge释放。


