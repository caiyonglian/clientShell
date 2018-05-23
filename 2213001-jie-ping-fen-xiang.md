# **2.2.1.1、截屏分享**

**1、js方法：**

//flag android截屏分三种模式截屏，flag表示采用的方式 0 截取activity 1 截取view 2 截取webview  IOS只支持一种，activity,故默认传0

screenShoot: function \(flag, success, error\) {

this.successHandler = success;

this.errorHandler = error;

var paramsList = \[flag\];

varuri = 'mobile-service://?object=screen&command=screenShot&params='+ JSON.stringify\(paramsList\);

callObject\(uri\);

}

}

**2、h5调用截屏分享的方法**

&lt;button onclick="boncAppEngine.screenShoot.screenShoot\(0,

function\(info\){output.innerHTML= 'screenShootInfo: '+info.codeInfo;},

function\(error\){output.innerHTML= 'screenShootError: '+error.description;}\)"&gt;screenshoot&lt;/button&gt;

