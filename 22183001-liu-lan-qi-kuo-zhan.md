# **2.2.1.8、浏览器扩展**

1、拦截器扩展

继承BNCWebViewURLInterceptor，实现performObject的方法

//具体的拦截处理操作。用户可以重写这个函数，根据参数做出自己的个性化处理。

-\(void\)performObject:\(NSString\*\)object command:\(NSString\*\)command withParam:\(id\)jsonObject{

 \[super performObject:object command:command withParam:jsonObject\];

 //code here

}

2、视图控制器 BNCWebViewController

//浏览器视图

@property \(nonatomic,strong\)UIWebView\* myWebView;

//返回按钮的图片

@property \(nonatomic,strong\)UIImage\* backBtnImage;

//关闭按钮的图片

@property \(nonatomic,strong\)UIImage\* closeBtnImage;

//进度条的高度

@property \(nonatomic,assign\)CGFloat progressBarHeight;

//进度条的颜色

@property \(nonatomic,strong\) UIColor\* progressBarTintColor;

//返回按钮

@property \(nonatomic,strong,readonly\)UIButton\* backBtn;

//关闭按钮

@property \(nonatomic,strong,readonly\)UIButton\* closeBtn;

// webView要显示的url

@property \(nonatomic,strong\)NSURL\* rootURL;

// webView的url拦截器

@property \(nonatomic,strong\)BNCWebViewURLInterceptor\* interceptor;

// 错误提示

@property \(nonatomic,strong\)BNCNetWorkErrorView\* errorView;

// 该控制器是否可以返回上一控制器

@property \(nonatomic,assign\) BOOL canGoBack;

// 进度条

@property \(nonatomic,strong\)BNCWebViewProgressView\*progressView;

// 进度生成器

@property \(nonatomic,strong\)BNCWebViewProgress\*progressProxy;

// 渐变样式

@property \(nonatomic,assign\)BarShadeStyle webBarShadeStyle;

@property \(nonatomic,strong\)UIColor\* barBgColor;

@property \(nonatomic,assign\)CGFloat webTopHeight;

@property \(nonatomic,assign\)CGFloat barShadeHeight;

//提供权限信息的代理

@property \(nonatomic,strong\) id&lt;URLInterceptorDelegate&gt; permissionDelegate;

//挂载自定义的拦截器

-\(void\)setInterceptor:\(BNCWebViewURLInterceptor \*\)newInterceptor;

//创建方法  当该控制器为导航控制器的根控制器时goBack应设为NO，否则应设为YES

-\(instancetype\)initWithURL:\(NSURL\*\)webURL canGoBack:\(BOOL\)goBack;

//此方法会在每次加载URL时对导航条状态进行还原（只还原导航条渐变样式及右侧items，并不影响左侧的items和导航条其他属性），可复写

- \(void\)restoreBarStyleDefault;

//当导航条由原生控制时，可通过以下两方法进行设置：

//对导航条右侧按钮和导航条背景样式进行设置 attributeDic的范例在文件底部注释中

- \(void\)setNavigationBarWithDictionary:\(NSDictionary \*\)attributeDic;

//只对导航条背景样式进行设置  attributeDic的范例为上述attributeDic中navigationBarStyle对应的数据

- \(void\)setNavigationBarBackgroundStyleWithDictionary:\(NSDictionary \*\)attributeDic;

//设置导航标题

- \(void\)setNavigationBarTitle:\(NSDictionary \*\)titleObj;

/\*\*

js回调方法

**@param** object js对象

**@param** handler js中对应的方法

**@param** param 传送的参数

\*/

-\(void\)callObject:\(NSString\*\)object withHandler:\(NSString\*\)handler param:\(id\)param;



//网页执行JS的入口

- \(NSString \*\)stringByEvaluatingJavaScriptFromString:\(NSString \*\)script;



/\*获取实时下载信息，此方法在下载进度发生变化时会调用，可复写

 @param url  当前正在下载的资源地址

 @param totalBytesWritten  已经写入沙盒的大小

 @param totalBytesExpectedToWrite 文件总大小

\*/

- \(void\)downloadUrl:\(NSURL \*\)url totalBytesWritten:\(int64\_t\)totalBytesWritten totalBytesExpectedToWrite:\(int64\_t\)totalBytesExpectedToWrite;

//查看网络附件

- \(void\)viewFileWithFileUrl:\(NSDictionary \*\)fileUrlObj;

//查看本地附件

- \(void\)viewFileWithFilePath:\(NSString \*\)filePath;

//以下为监听webview加载URL过程中触发的方法,子类可复写

//是否允许加载url

- \(BOOL\)webViewShouldStartLoadUrl:\(NSURL \*\)url navigationType:\(UIWebViewNavigationType\)navigationType;

//加载完成

- \(void\)webViewDidFinishLoadUrl:\(NSURL \*\)url;

//加载失败

- \(void\)webViewDidFailLoadUrl:\(NSURL \*\)url WithError:\(NSError \*\)error;

//设置导航左侧显示关闭和返回按钮的方法，如有特殊需求可复写

-\(void\)loadBackButtonsNeedShutDwonButton:\(BOOL\)needShutDown canGoBack:\(BOOL\)goBack;



