# **2.2.1.10、关闭浏览器**

**1、js方法：**

//关闭浏览器

 shutdown:function\(\){

var uri = 'mobile-service://?object=self&command=shutdown';

 callObject\(uri\);

 }

**2、H5的调用方法**

&lt;button onclick="boncAppEngine.shutdown\(\)"&gt;exit&lt;/button&gt;

