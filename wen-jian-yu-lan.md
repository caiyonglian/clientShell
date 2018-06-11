# **2.2.1.9、文件预览**

**1、js方法：**

//文件

file:{

 //查看文件 fileObj中文件地址对应的key为fileUrl

 //例：JSON.stringify\({'fileUrl':'http%3a%2f%2f172.16.63.108%3a8080%2fresources%2fdemo.docx.zip'}\)

successHandler:function\(success\){},

errorHandler:function\(error\){},

viewFile: function\(fileObj,success,error\) {

this.successHandler = success;

this.errorHandler = error;

varuri = 'mobile-service://?object=file&command=viewFile&params='+fileObj+'';

 callObject\(uri\);

}

}

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.file.viewFile\(JSON.stringify\({'fileUrl':'http%3a%2f%2f172.16.63.108%3a8080%2fresources%2fdemo.docx.zip'}\),

function\(success\){

output.innerHTML= 'info: '+success.description;

},function\(error\){

output.innerHTML = 'info: '+error.description;

}\)"&gt;打开文件&lt;/button&gt;

