1.lldb debug 很多对象p不出来：
	
	step1:expr @import UIKit<br>
	step2:p UIScreen.mainScreen.bounds

2.用宏定义检测block是否可用!

 	#define BLOCK_EXEC(block, ...) if (block) 	{ block(__VA_ARGS__); };    
 
	// 宏定义之前的用法  
	/* 
	if (completionBlock)   
	{   
   	 completionBlock(arg1, arg2);   
	}   
  	*/  
   
	// 宏定义之后的用法  
	BLOCK_EXEC(completionBlock, arg1, arg2);


8.读取本地图片(from 夏夏)
	
 	#define LOADIMAGE(file,ext) [UIImage imageWithContentsOfFile:［NSBundle mainBundle]pathForResource:file ofType:ext］
 
	//定义UIImage对象
 	#define IMAGE(A) [UIImage imageWithContentsOfFile:［NSBundle mainBundle] pathForResource:A ofType:nil］

9.iOS开发----Xcode7升级之后插件无法使用与不小心点击Skipbundle的解决办法

	1. 首先查看 Xcode 的 UUID,在终端执行

	defaults read /Applications/Xcode.app/Contents/Info DVTPlugInCompatibilityUUID

	会得到一串 UUID 码

	2. 找到 Xcode 插件所在的目录

	~/Library/Application Support/Developer/Shared/Xcode/Plug-ins

	选择已安装的插件如:VVDocumenter-Xcode,右键显示包内容,找到 info.plist

	找到DVTPlugInCompatibilityUUIDs的项目，添加一个Item，Value的值为之前Xcode的UUID，保存.
	
	
