# **2.2.1.6、相机拍照**

**1、js方法：**

//相机需要获取的媒体类型

mediaType:{

JPEG:0,

PNG:1

},

//相机对象camera

camera: {

//原生拍照成功的回调句柄，其中包括照片数据Base64编码的字符串，以及照片的类型；

successHandler: function\(imageInfo\){},

//原生拍照发生错误的回调句柄

errorHandler: function\(errror\){},

//原生用户取消拍照的回调句柄

cancelHandler: function\(\){},

//js调用拍照

takePhoto: function\(mediaType,quality,success,cancle,error\){

this.successHandler=success;

this.cancleHandler=cancle;

this.errorHandler=error;

var uri='mobile-service://?object=camera&command=takePhoto&params=\['+mediaType+','+quality+'\]';

callObject\(uri\);

}

}

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.camera.takePhoto\(boncAppEngine.mediaType.JPEG,50,

function \(imageInfo\) {

var image= document.getElementById\('iamge'\);

image.src=imageInfo.dataURL;

},

null,

function \(error\){

output.innerHTML= 'TakePhotoError: '+error.description;

}\)"&gt;camera&lt;/button&gt;

