# **2.2.1.12、APP的版本信息**

**1、js方法：**

p.p1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px Menlo; color: \#008400; background-color: \#ffffff}  
p.p2 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px Menlo; color: \#000000; background-color: \#ffffff}  
p.p3 {margin: 0.0px 0.0px 0.0px 0.0px; font: 11.0px Menlo; color: \#272ad8; background-color: \#ffffff}  
span.s1 {color: \#000000}  
span.s2 {color: \#ba2da2}

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

varuri='mobile-service://?object=appInfo&command=getAppVersion';

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

