# **2.2.2、极光推送**

BCMessageNotiService继承自JPUSHService

单独封装了极光的消息注册。

+\(void\)registerRemoteNotificationWithOption:\(NSDictionary \*\)launchingOption

 appKey:\(NSString \*\)appKey

 channel:\(NSString \*\)channel

 apsForProduction:\(BOOL\)isProduction;

使用方法：

\[BCMessageNotiService registerRemoteNotificationWithOption:launchOptions appKey:\[keyDic valueForKey:@"JPushAppKey"\] channel:@"Publish channel" apsForProduction:YES\];

其他的api参照极光推送api。



