# **2.2.1.7、二维码扫描**

**1、js方法：**

codeScanner: {

//原生扫描成功的回调句柄，其中包括用户的经度、纬度、移动速度及其他

successHandler: function\(codeInfo\){},

//原生扫描失败的回调句柄

errorHandler: function\(error\){},

//原生用户取消扫描操作的回调句柄

cancleHandler: function\(\){},

//js调用扫描

scan: function\(success,cancle,error\){

this.successHandler=success;

this.cancleHandler=cancle;

this.errorHandler=error;

var uri='mobile-service://?object=codeScanner&command=scan';

callObject\(uri\);

}

}

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.codeScanner.scan\(

function \(info\){output.innerHTML= 'CodeScanInfo: '+info.codeInfo;},

null,

function \(error\){output.innerHTML= 'CodeScanError: '+error.description;}\)"&gt;scanCode&lt;/button&gt;

