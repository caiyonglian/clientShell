# **2.2.1.11、内容分享**

**1、js方法：**

//通过友盟分享文本内容及链接 分享图片到微信等公众平台

systemShare:{

successHandler: function \(successo\) {

},

errorHandler: function \(error\) {

},

 //contents,可以传输的内容 contents内传输的是文本内容与对应的链接格式为command=link JSON.stringify\({'title':'abcdX','desc':'sssss','icon':'http://','shareUrl':'http://www.baidu.com'}\)

 //command=image JSON.stringify\({'icon':'http://'}\)

systemShare: function \(command,contents,success, error\) {

this.successHandler = success;

this.errorHandler = error;

varuri = 'mobile-service://?object=share&command='+command+'&params='+contents;

 callObject\(uri\);

}

}

**2、h5调用分享的方法**

注：分享地址需要用urlencode进行编码。

//分享文本链接

&lt;buttononclick="boncAppEngine.systemShare.systemShare\('link',JSON.stringify\({'title':'abcdX','desc':'sssss','icon':'https%3a%2f%2ftimgsa.baidu.com%2ftimg%3fimage%26quality%3d80%26size%3db9999\_10000%26sec%3d1528107812526%26di%3d7a6c20e3c75e0aa3d4bcff9c2a7475c4%26imgtype%3d0%26src%3dhttp%3a%2f%2fimg.zcool.cn%2fcommunity%2f0181e458330aa7a801219c770bd49e.png','shareUrl':'https%3a%2f%2fbaike.baidu.com%2fitem%2f%e6%b7%b1%e8%93%9d%e8%89%b2%e7%9a%84%e6%83%85%e4%b9%a6%2f10979182%3ffr%3daladdin'}\),

 function\(info\){output.innerHTML= 'shareInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'shareError: '+error.description;}\)"&gt;分享链接&lt;/button&gt;

//分享图片

&lt;buttononclick="boncAppEngine.systemShare.systemShare\('image',JSON.stringify\({'icon':'https%3a%2f%2ftimgsa.baidu.com%2ftimg%3fimage%26quality%3d80%26size%3db9999\_10000%26sec%3d1528107812526%26di%3d7a6c20e3c75e0aa3d4bcff9c2a7475c4%26imgtype%3d0%26src%3dhttp%3a%2f%2fimg.zcool.cn%2fcommunity%2f0181e458330aa7a801219c770bd49e.png'}\),

 function\(info\){output.innerHTML= 'shareInfo: '+info.codeInfo;},

 function\(error\){output.innerHTML= 'shareError: '+error.description;}\)"&gt;分享图片&lt;/button&gt;

