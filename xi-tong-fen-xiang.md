# **2.2.1.11、系统分享**

**1、js方法：**

//分享文本内容或链接

systemShare:{

successHandler: function \(successo\) {

},

errorHandler: function \(error\) {

},

//contents,可以传输的内容 command=text contents内传输的是文本内容 command=link对应的链接

systemShare: function \(command,contents,success, error\) {

this.successHandler = success;

this.errorHandler = error;

var paramsList = \[contents\];

var uri = 'mobile-service://?object=share&command='+command+'&params='+JSON.stringify\(paramsList\);

 callObject\(uri\);

}

}

**2、h5调用分享的方法**

&lt;button onclick="boncAppEngine.systemShare.systemShare\('link','http://www.baidu.com',

 function\(info\){output.innerHTML= 'shareInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'shareError: '+error.description;}\)"&gt;systemShare&lt;/button&gt;



&lt;buttononclick="boncAppEngine.systemShare.systemShare\('text','test content',

 function\(info\){output.innerHTML= 'shareInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'shareError: '+error.description;}\)"&gt;systemShare&lt;/button&gt;

