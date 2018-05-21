# **2.2.1.4、设备信息**

可以获取设备的名称，设备型号，设备的系统名称，系统版本号，UUID，wifi的名称与wifi的mac地址等信息。

**1、js方法：**

//设备对象

device: {

//原生获取设备信息成功的回调句柄，其中包括用户的经度、纬度、移动速度及其他

successHandler: function\(deviceInfo\){},

//原生获取设备信息失败的回调句柄

errorHandler: function\(error\){},

//js调用获取设备信息

getDeviceInfo: function\(success,error\){

this.successHandler=success;

this.errorHandler=error;

var uri='mobile-service://?object=device&command=getDeviceInfo';

callObject\(uri\);

}

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.device.getDeviceInfo\(

function \(device\) {

output.innerHTML='name:'+device.name+'&lt;/br&gt; model:'+device\['detailModel'\]+'&lt;/br&gt;platform:'+device.platform+'&lt;/br&gt;version:'+device\['version'\];

},

function \(error\){

output.innerHTML= 'GetDeviceInfoError: '+error.description;

}\)"&gt;deviceInfo&lt;/button&gt;

