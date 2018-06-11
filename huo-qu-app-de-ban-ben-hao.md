# **2.2.1.12、APP的版本信息**

**1、js方法：**

//应用信息

appInfo: {

//原生获取应信息成功的回调句柄，其中包括应用的版本

successHandler: function\(appInfo\){},

//原生获取应用信息失败的回调句柄

errorHandler: function\(error\){},

//js调用获取应用的版本号

getAppVersion:function\(success,error\){

this.successHandler=success;

this.errorHandler=error;

var uri='mobile-service://?object=appInfo&command=getAppVersion';

callObject\(uri\);

}

}

**2、h5调用分享的方法**

&lt;button onclick="boncAppEngine.appInfo.getAppVersion\(

function \(appInfo\) {

output.innerHTML='AppVersion:'+appInfo.versionNo;

},

function \(error\){

output.innerHTML= 'GetAppVersionError: '+error.description;

}\)"&gt;appVersion&lt;/button&gt;

