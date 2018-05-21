# **2.2.1.3、通讯录**

**1、js方法：**

//手机通讯录对象contacts

contacts: {

//原生创建联系人成功的回调句柄

newContactSuccessHandler: function\(conatactInfo\){},

//原生创建联系人取消的回调句柄

newContactCancleHandler: function\(\){},

//原生访问联系人出错的回到句柄

newContactErrorHandler: function\(errror\){},

//js调用创建联系人

newContact: function\(success,cancle,error\){

this.newContactSuccessHandler=success;

this.newContactCancleHandler=cancle;

this.newContactErrorHandler=error;

var uri='mobile-service://?object=contacts&command=newContact';

callObject\(uri\);

},

//选择联系人成功的回调句柄

chooseContactSuccessHandler: function\(conatactInfo\){},

//选择联系人取消的回调句柄

chooseContactCancleHandler: function\(\){},

//选择联系人错误的回调句柄

chooseContactErrorHandler: function\(errror\){},

//js调用选择联系人

chooseContact: function\(success,cancle,error\){

this.chooseContactSuccessHandler=success;

this.chooseContactCancleHandler=cancle;

this.chooseContactErrorHandler=error;

var uri='mobile-service://?object=contacts&command=chooseContact';

callObject\(uri\);

}

},

**2、H5调用通讯录的方法**

**//创建联系人**

&lt;button onclick="boncAppEngine.contacts.newContact\(

function \(contactInfo\){output.innerHTML= 'contactID: '+contactInfo\['id'\]},

function\(\){},

function\(error\){output.innerHTML= 'newContactError: '+error.description;}\)"&gt;create contact&lt;/button&gt;

**//选择联系人**

&lt;button onclick="boncAppEngine.contacts.chooseContact\(

function\(conatactInfo\){

},

function\(\){},

function\(error\){output.innerHTML= 'chooseContactError: '+error.description;}\)"&gt;choose contact&lt;/button&gt;

