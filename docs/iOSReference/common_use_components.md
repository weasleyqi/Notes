#Common Use Components:

Component Name | URL | Description | Note
:--:|:--:|:--
MJRefresh|<https://github.com/CoderMJLee/MJRefresh>|用法最简单的下拉,上拉刷新框
RDVTabBarController|<https://github.com/robbdimitrov/RDVTabBarController>|Customer TabBar ViewController
TPKeyboardAvoiding|<https://github.com/michaeltyson/TPKeyboardAvoiding>|用户键盘弹出自动计算高度，进行屏幕滚动操作。|未验证过
MJExtension|<https://github.com/CoderMJLee/MJExtension>|JSon->Model <br> Model->Json<br> Json Array->Model Array<br> Model Array->Json Array<br>直接将Json转换成Model|比较轻量级，类似控件：**Mantle**，**JSONModel**
ReactiveCocoa|<https://github.com/ReactiveCocoa/ReactiveCocoa>|一个kvo组件，用来做消息监听|Hard to Understand<br>一方面是 ReactiveCocoa 带来的编程习惯上的改变实在太大，ReactiveCocoa 和 MVVM 的学习成本还是很高。另一方面是 ReactiveCocoa 在代码可读性、可维护性和协作上不太友好。
Masonry|<https://github.com/SnapKit/Masonry>|Masonry是一个轻量级的布局框架，拥有自己的描述语法，采用更优雅的链式语法封装自动布局，简洁明了并具有高可读性。|
BeeFramework|<https://github.com/gavinkwoe/BeeFramework>|类似 HTML + CSS 的排版<br>但是受限于它自身的影响力以及框架的复杂性，一直没有很大的成功。|





<br><br><br><br>
#Plugin
Plugin Name | URL | Description|Note
:--:|:--:|--|--
VVDocumenter-Xcode|<https://github.com/onevcat/VVDocumenter-Xcode>|自动注解
FuzzyAutocompletePlugin|<https://github.com/FuzzyAutocomplete/FuzzyAutocompletePlugin>|自动补全系统添加了模糊匹配|值得推荐
deriveddata-exterminator|<https://github.com/kattrali/deriveddata-exterminator>|Sometimes Xcode needs a friendly helping hand with cleaning out the Derived Data for a project. The Exterminator makes this quick and easy.|
ZLXCodeLine|<https://github.com/MakeZL/ZLXCodeLine>|代码行数排行榜，主要用于监控自己的代码是否规范。|
XAlign|<https://github.com/qfish/XAlign>|自动代码对齐，使得代码更加好看。|



<br><br><br><br><br>
##项目经验

* 框架搭建的时候，要考虑好App中各功能点的实现方案。设计好相关文件目录，封装相关类文件。
* 封装整理相关方法，比如BaseViewController中包括，基本ui，顶部导航条，左按钮，右按钮，标题，相关点击事件，显示/隐藏loading，网络请求失败统一处理方法，上拉/下拉刷新绑定，刷新显示/隐藏。分析项目中的功能相同模块，封装对应操作，相同功能代码维护一份。
* 考虑好刷新机制，比如A页面进入B页面，B更新后，返回后A页面的刷新，如果采用block/delegate的方法，可以统一进行设计。或者多个页面之间的数据刷新，采用通知的方式（KVO），进行更新操作。尽量开发阶段，就把可能出现的问题提前解决。
* 确定是否进行相关页面统计，比如加友盟的页面统计，需要设置相关view的viewWillAppear和viewWillDisappear（）
* ViewController中初始化view和数据请求后刷新view代码分离，封装整理好网络请求前和请求后的操作，考虑好下拉刷新页面和上拉加载更多的相关数据请求和处理。考虑有网状态下的数据缓存以及无网状态下的缓存数据加载
* 提前做好相关页面的跳转，代码解耦，不断优化和重构代码。发现问题或者有更好的解决方案，尽量早期就进行修改，避免修修补补，方便后期维护和扩展。在可以接受的情况下，可以牺牲一些系能，保持逻辑简单，便于维护。
* 通过代码写view计算坐标时，尽量参考上一个元素的坐标和宽高，这样当一个元素位置或宽高发生变化时，其他元素基本都能随着发生变化。
* 数据处理能放在服务器端处理就由服务器端处理，前台就进行无脑显示。
* 考虑程序的兼容性，32位和64位一些变量的值不同，注意值的越界问题。注意程序的内存问题，和使用过程中的内存变化。
* 考虑信息的安全性，沙盒存储的信息可以被查看修改，重要信息请加密。


<br><br><br>
##待整合Points
	1 URL encode decode
	2 MD5 
	3 Null String convert
	4 倒计时
	5 编辑状态页面上移
	6 打电话
	7 load URLRequest
	8 图片size的处理
	9 操作完之后的block
	10 category
	
	
	
	