# CMSTP

微软连接管理器配置文件安装器是一个用来安装链接管理服务的配置文件的命令行工具。CMSTP.exe可以接收一个安装信息文件（INF）作为参数，并且安装一个用于远程访问链接的配置文件。

（squiblydoo技术参考链接：

[https://www.carbonblack.com/2016/04/28/threat-advisory-squiblydoo-continues-trend-of-attackers-using-native-os-tools-to-live-off-the-land/](https://www.carbonblack.com/2016/04/28/threat-advisory-squiblydoo-continues-trend-of-attackers-using-native-os-tools-to-live-off-the-land/)

[https://www.brimorlabsblog.com/2016/04/very-quick-blog-post-on-squiblydoo.html](https://www.brimorlabsblog.com/2016/04/very-quick-blog-post-on-squiblydoo.html)

）

攻击者可能向CMSTP.exe提供被恶意命令感染的INF文件。类似于 Regsvr32/“Squiblydoo”技术，CMSTP.exe可能被滥用为从远程服务器加载、执行DLL或者COM scriptlet（SCT）的工具。这种执行方式可能绕过Applocker或者其他白名单限制（因为CMSTP.exe是合法的、签名的微软程序）。

CMSTP.exe也可以用来绕过UAC，并通过自动提升权限（自动过UAC）的COM接口执行恶意INF文件中的命令。

