# **2.2.1.10、关闭浏览器**

**1、js方法：**

//文件

file:{

//查看文件 fileObj中文件地址对应的key为fileUrl

successHandler:function\(success\){},

errorHandler:function\(error\){},

viewFile: function\(fileObj,success,error\) {

this.successHandler = success;

this.errorHandler = error;

var uri = 'mobile-service://?object=file&command=viewFile&params='+fileObj+'';

callObject\(uri\);

}

}

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.file.viewFile\('[http://172.16.63.108:8080/resources/demo.docx.zip](http://172.16.63.108:8080/resources/demo.docx.zip)',

function\(success\){

output.innerHTML= 'info: '+success.description;

},function\(error\){

output.innerHTML = 'info: '+error.description;

}\)"&gt;打开文件&lt;/button&gt;

