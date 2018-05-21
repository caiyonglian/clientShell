# **2.2.1.2、百度地图定位**

**1、js方法：**

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

var uri='mobile-service://?object=locationManager&command=start';

callObject\(uri\);

},

//js调用停止定位（当页面不在需要定位功能时，请务必调用此函数关闭定位，保持电量）

stop: function\(\){

var uri='mobile-service://?object=locationManager&command=stop';

callObject\(uri\);

}

}

**2、h5调用定位的方法**

//开始定位

&lt;button onclick="boncAppEngine.locationManager.start\(

 function \(location\) {

 output.innerHTML='longitude:'+location.longitude+'&lt;/br&gt; latitude:'+location\['latitude'\]+'&lt;/br&gt;speed:'+location.speed+'&lt;/br&gt;timestamp:'+location\['timestamp'\];},

 function \(error\){

 output.innerHTML= 'locationError: '+error.description;

 }\)"&gt;start location&lt;/button&gt;

//结束定位

&lt;button onclick="boncAppEngine.locationManager.stop\(\)"&gt;stop location&lt;/button&gt;

