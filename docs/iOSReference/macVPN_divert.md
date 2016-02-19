#Mac（OSX）使用VPN小技巧——国内外访问分流

自从Mac用上了VPN，科学的上网让我的小Mac充满了活力。巴特，也带来了一个大问题，开启VPN的时候访问国内网站有时候特别慢。难道要我每次访问国内都要断开，访问国外再连上，接受无能啊！！！实际上，大部分windows的VPN客户端软件，都集成国内外分流的功能，非常便捷，而Mac上目前还没有类似的软件有此功能，好吧，只能自己动手，丰衣足食了。

Mac下国内外访问分流有啥好处？
连上VPN以后，不会影响访问国内网站的速度
有些VPN提供的是流量套餐，如果不分流，一个月流量伤不起啊
如何实现Mac下VPN的国内外分流？
Mac下的分流方法来源于chnroute这个项目，对作者表示衷心的感谢
项目地址：https://github.com/jimmyxu/chnroutes
此项目不仅仅是针对Mac，而且同时支持windows/linux，以及基于linux的路由器。

下面就说下Mac下的使用步骤：
1. 首先，你要弄一个VPN并且设置好PPTP，免费VPN之前我介绍过一个合集，可以看这里;
2. 下载chnroutes.py这个文件，比如保存到下载里面，下载地址
3. 打开终端进入下载文件所在的目录，执行python chnroutes.py -p mac，在该目录下会生成2个文件，ip-up和ip-down；
macbookair:~ Peter$ cd Downloads
macbookair:Downloads Peter$ python chnroutes.py -p mac
Fetching data from apnic.net, it might take a few minutes, please wait...
For pptp on mac only, please copy ip-up and ip-down to the /etc/ppp folder,don't forget to make them executable with the chmod command.
4. 打开Finder进入下载，可以找到刚刚生成的2个文件，选中并复制这2个文件；按下快捷键command+shift+g，弹出的地方输入/etc/ppp，进入此目录，粘贴；
5. 回到终端，进入目录（/etc/ppp）执行：sudo chmod a+x ip-up ip-down
macbookair:Downloads Peter$ cd /etc/ppp
macbookair:ppp Peter$ sudo chmod a+x ip-up ip-down
（这一步可能会提示输入系统密码）
好了，Done！连上VPN测试一下吧。

如何测试是否成功？
比较简单的测试方法是打开2个ip地址查询网站。如果一切正常，连上vpn以后，打开ip138，会显示你本来的ip地址（你还在国内），打开这个网站，会显示vpn服务器的ip地址（你到国外了）。

高端一点的，可以在终端输入traceroute www.baidu.com以及traceroute www.youtube.com，看看访问国内网站和国外网站的路由情况。

如果我不想要分流了，怎么破？
直接把/etc/ppp下面那2个文件删了就行了。