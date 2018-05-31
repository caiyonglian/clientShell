# **2.2.1.11、系统分享**

**1、js方法：**

//分享文本内容及链接

systemShare:{

successHandler: function \(successo\) {

},

errorHandler: function \(error\) {

},

 //contents,可以传输的内容 contents内传输的是文本内容与对应的链接格式为JSON.stringify\({'title':'abcdX','shareUrl':'http://www.baidu.com'}\)

systemShare: function \(contents,success, error\) {

this.successHandler = success;

this.errorHandler = error;

varuri = 'mobile-service://?object=share&command=link&params='+contents;

 callObject\(uri\);

}

}

**2、h5调用分享的方法**

注：分享地址需要用urlencode进行编码。

&lt;button onclick="boncAppEngine.systemShare.systemShare\(JSON.stringify\({'title':'abcdX','shareUrl':'https%3a%2f%2fbaike.baidu.com%2fitem%2f%e6%b7%b1%e8%93%9d%e8%89%b2%e7%9a%84%e6%83%85%e4%b9%a6%2f10979182%3ffr%3daladdin'}\),

 function\(info\){output.innerHTML= 'shareInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'shareError: '+error.description;}\)"&gt;systemShare&lt;/button&gt;

