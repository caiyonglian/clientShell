# 2、ClientShell使用手册

**2.1、ClientShell的全局配置**

配置文件位于BAE\_react/Info.plist中，如下图：

![](/assets/屏幕快照 2018-05-21 15.34.22.png)1、BCFlowConfig，框架流程设置

BCFlowType设置为0时，则根据BCBrowserIndexPage的设置加载一个浏览器页。

![](/assets/屏幕快照 2018-05-21 15.56.15.png)MenuGroupIcon：是指浏览器的图标，可以不设置

MenuGroupTitle：网页的标题

MenuGroupURL：网页地址

MenuGroupIsLocaltion：设置是否需要加载本地的网页

MenuGroupLocaltionURL：加载本地网页对应的文件夹路径

BCFlowType设置为1是代表是ReactNative项目。默认启动main.jsbundle这个页面。

BCFlowType设置为2时是代表原生项目，则启动BCNativeViewControllers中设置的原生页面。

2、BCKeyConfig是第三方类库对应的appkey，通过修改下面的配置可以实现appkey的替换。

BaiduMapKey是百度地图的appKey，

BaiduMobStatAppID是百度统计的appid

JPushAppKey是极光推送的appkey。

3、BCThemeConfig主题样式设置，通过此处可以设置应用的导航样式与加载条的颜色。

NaviBar的样式![](/assets/屏幕快照 2018-05-21 15.43.12.png)可以设置NaviBar的字体的颜色与字体及设置NaviBar的导航背景色。

通过WebViewProgressBarTintColor可以设置可以修改浏览器加载进度条的颜色。



**2.2、ClientShell的使用方法**

