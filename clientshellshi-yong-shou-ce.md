**2.2、ClientShell的使用方法**

JS与原生的交互，见js文件

BoncAppEngine.js

![](/assets/屏幕快照 2018-05-21 16.54.44.png)



**1、截屏分享**

**js方法：**

screenShoot:{

successHandler: function \(successo\) {

},

errorHandler: function \(error\) {

},

 //flag android截屏分三种模式截屏，flag表示采用的方式 0 截取activity 1 截取view 2 截取webview  IOS只支持一种，activity,故默认传0 &params=' + JSON.stringify\(flag\) + '

screenShoot: function \(flag, success, error\) {

this.successHandler = success;

this.errorHandler = error;

varuri = 'mobile-service://?object=screen&command=screenShot&params=\['+flag+'\]';

 callObject\(uri\);

}

}

**h5调用截屏分享的方法**

&lt;buttononclick="boncAppEngine.screenShoot.screenShoot\(0,

 function\(info\){output.innerHTML= 'screenShootInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'screenShootError: '+error.description;}\)"&gt;screenshoot&lt;/button&gt;

**2、百度定位**

**js方法：**

//定位对象locationManager；

locationManager: {

 //原生定位成功的回调句柄，其中包括用户的经度、纬度、移动速度及其他

successHandler: function\(location\){},

 //原生定位失败的回调句柄

errorHandler: function\(error\){},

 //js调用开始定位，原生平台（ios、android）会通过原生代码调用handler回调

start: function\(success,error\){

this.successHandler=success.bind\(this\);

this.errorHandler=error.bind\(this\);

varuri='mobile-service://?object=locationManager&command=start';

 callObject\(uri\);

},

 //js调用停止定位（当页面不在需要定位功能时，请务必调用此函数关闭定位，保持电量）

stop: function\(\){

varuri='mobile-service://?object=locationManager&command=stop';

 callObject\(uri\);

}

}

**h5调用定位的方法**

4、百度统计

5、极光推送

2、浏览器

