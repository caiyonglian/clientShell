# **2.2.1.8、设置导航**

**1、js方法：**

//设置导航

webNavigation: {

successHandler: function\(success\) {},

errorHandler: function\(error\) {},

//点击右上角导航后的操作

parentItemHandler:function\(id\){},

//点击展出的弹出框的操作

childItemHandler:function\(id\){},

//navigationBg控制背景，navigationModule控制导航栏显示

setNaviagtionShowStyle: function\(navigationSetting, success, error\) {

this.successHandler = success;

this.errorHandler = error;

var uri = 'mobile-service://?object=webNavigation&command=navigationShowStyle&params='+navigationSetting+'';

callObject\(uri\);

},

//设置导航标题 titleObj中标题对应的key为navigationTitle

setNaviagtionTitle: function\(titleObj\) {

var uri = 'mobile-service://?object=webNavigation&command=setNaviagtionTitle&params='+titleObj+'';

callObject\(uri\);

}

}

**2、H5的调用方法**  


&lt;button style="height: 100px; width: 100px; position: absolute;top: 200px; right: 10px;" onclick="boncAppEngine.webNavigation.setNaviagtionTitle\(JSON.stringify\({'titleKey':'abcdX'}\)\)"&gt;导航标题按钮&lt;/button&gt;

&lt;button style="height: 1000px; width: 100px; position: absolute;top: 500px; right: 0px;" onclick="boncAppEngine.webNavigation.setNaviagtionShowStyle\(JSON.stringify\({

 'navigationBarStyle': {

 'webTopHeight': '500',

 'barBgColor': 'ff6b6fdd',

 'barShadeStyle': '1'

 },

 'naviRightBtnList': \[{

 'id': '0',

 'netImageUrl': 'http://www.126.com/favicon.ico',

 'localImageName': '我',

 'btnTitleName': '名称0',

 'childElement': \[{

 'id': '0',

 'netImageUrl': 'https://www.baidu.com/img/bd\_logo1.png',

 'localImageName': '我',

 'btnTitleName': '我真是个程序员，绝对经典绝对经典搭建见',

 'subListBgColor': 'F05677',

 'subListTextColor': '022135'

 },

 {

 'id': '1',

 'netImageUrl': 'https://www.baidu.com/img/bd\_logo1.png',

 'localImageName': 'fuck',

 'btnTitleName': '我',

 'subListBgColor': 'F05677',

 'subListTextColor': '022135'

 }

 \]

 },

 {

 'id': '1',

 'localImageName': 'fuck',

 'btnTitleName': '名称1',

 'childElement': \[{

 'id': '2',

 'netImageUrl': 'https://www.baidu.com/img/bd\_logo1.png',

 'localImageName': 'fuck',

 'btnTitleName': '我',

 'subListBgColor': 'F05677',

 'subListTextColor': '022135'

 },

 {

 'id': '3',

 'netImageUrl': 'https://www.baidu.com/img/bd\_logo1.png',

 'localImageName': '我',

 'btnTitleName': '我',

 'subListBgColor': 'F05677',

 'subListTextColor': '022135'

 }

 \]

 }

 \]

 }

 \)\)"&gt;测试按钮&lt;/button&gt;

