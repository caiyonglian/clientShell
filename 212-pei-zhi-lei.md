# **2.2.3、配置管理类**

配置管理类：BCConfigManage

/\*\*

获取配置文件所在的资源bundle

**@return** \[NSBundle mainBundle\]

使用示例:

NSBundle \*bundle = \[\[BCConfigManage sharedConfigManager\]getResourceBundle\];

\*/

-\(NSBundle\*\)getResourceBundle;



/\*\*

根据图片名称与图片类型从资源包中获取图片.

**@param** imgName 图片名称

**@param** imageType 图片类型,eg: png, jpg,etc

**@return** a image instance

使用示例:

\[\[BCConfigManage sharedConfigManager\]imageItemForName:@"imageName" ofType:@"png"\];

\*/

-\(UIImage\*\)imageItemForName:\(NSString\*\)imgName ofType:\(NSString\*\)imageType;



/\*\*

根据图片名称与图片类型及图片在资源包中的相对路径从资源包中获取图片.

**@param** imgName 图片名称

**@param** imageType 图片类型,eg: png, jpg,etc

**@param** subPath  图片在资源包中的相对路径

**@return** a image instance

使用示例:

\[\[BCConfigManage sharedConfigManager\]imageItemForName:@"imageName" ofType:@"png"inDirectory:@"images"\];

\*/

-\(UIImage\*\)imageItemForName:\(NSString \*\)imgName ofType:\(NSString \*\)imageType inDirectory:\(NSString\*\)subPath;



/\*\*

配置文件中获取配置信息字典中的具体项的值

**@param** 某项的keyPath，eg：BCKeyConfig

**@return** id instance

使用示例:

NSDictionary \*keyDic =\[\[BCConfigManage sharedConfigManager\]configInfoForKeyPath:@"BCKeyConfig"\];

\*/

-\(id\)configInfoForKeyPath:\(NSString\*\)keyPath;



/\*\*

获取配置信息字典中的颜色值

The Color must be in RGBA colore space. The range of color component is 0.0~1.0 and color component is seperated wiht ",". color eg：0.137, 0.537, 0.988, 1.0

**@param** 颜色对应的keyPath eg：BCThemeConfig.NaviBar.TextColor

**@return** UIColor a UIColor instance decoded from the configInfo

使用示例：

UIColor\*naviBarTextColor = \[\[BCConfigManage sharedConfigManager\] colorConfigInfoForKeyPath:@"BCThemeConfig.NaviBar.TextColor"\];

\*/

-\(UIColor\*\)colorConfigInfoForKeyPath:\(NSString\*\)keyPath;  


/\*\*

获取配置信息字典中的字体信息

The string presentation for Font is in format "B14" or "b14". "B" and "b" stand for system blod , the number stand for font size.

**@param** 字体对应的keyPath eg：BCThemeConfig.NaviBar.TextFont

**@return** UIFont a UIFont instance decoded from the configInfo

使用示例：

UIFont\*naviBarTitleFont = \[\[BCConfigManage sharedConfigManager\] fontConfigInfoForKeyPath:@"BCThemeConfig.NaviBar.TextFont"\];

\*/

-\(UIFont\*\)fontConfigInfoForKeyPath:\(NSString\*\)keyPath;



