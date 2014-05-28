openwrt-reaver
==============

在很多家用路由器上，刷openwrt，总想放进更多功能。然而，经常发现rom不够用。比如，刷了luci web界面，再想添加reaver 就不行。

这里采用的方法是压缩lua代码（使用LuaSrcDiet），以减少luci占用的空间。以后还会再压缩css/js/html代码。

大多数情况下，我们并不想花一天的时间来编译openwrt源码，因此，这里使用了openwrt imagebuilder来构造固件。
刷入固件成功后，使用方法如下：

telnet 路由器
＃screen
＃airmon-ng start wlan0
＃wash -i mon0
＃reaver -i mon0 -b XX:XX:XX:XX:XX:XX

ctrl +a+d

＃screen -ls
//就可以看到现在后台运行的进程id。

//再次进入
telnet 路由器
＃screen -r 进程id
