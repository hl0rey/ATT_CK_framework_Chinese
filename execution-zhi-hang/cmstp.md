# CMSTP

微软连接管理器配置文件安装器是一个用来安装链接管理服务的配置文件的命令行工具。CMSTP.exe可以接收一个安装信息文件（INF）作为参数，并且安装一个用于远程访问链接的配置文件。

（squiblydoo技术参考链接：

[https://www.carbonblack.com/2016/04/28/threat-advisory-squiblydoo-continues-trend-of-attackers-using-native-os-tools-to-live-off-the-land/](https://www.carbonblack.com/2016/04/28/threat-advisory-squiblydoo-continues-trend-of-attackers-using-native-os-tools-to-live-off-the-land/)

[https://www.brimorlabsblog.com/2016/04/very-quick-blog-post-on-squiblydoo.html](https://www.brimorlabsblog.com/2016/04/very-quick-blog-post-on-squiblydoo.html)

）

攻击者可能向CMSTP.exe提供被恶意命令感染的INF文件。类似于 Regsvr32/“Squiblydoo”技术，CMSTP.exe可能被滥用为从远程服务器加载、执行DLL或者COM scriptlet（SCT）的工具。这种执行方式可能绕过Applocker或者其他白名单限制（因为CMSTP.exe是合法的、签名的微软程序）。

CMSTP.exe也可以用来绕过UAC，并通过自动提升权限（自动过UAC）的COM接口执行恶意INF文件中的命令。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Disable or Remove Feature or Program](https://attack.mitre.org/mitigations/M1042) | CMSTP.exe may not be necessary within a given environment \(unless using it for VPN connection installation\). |
| [Execution Prevention](https://attack.mitre.org/mitigations/M1038) | Consider using application whitelisting configured to block execution of CMSTP.exe if it is not required for a given system or network to prevent potential misuse by adversaries. |

## 例子

| Name | Description |
| :--- | :--- |
| [Cobalt Group](https://attack.mitre.org/groups/G0080) | [Cobalt Group](https://attack.mitre.org/groups/G0080) has used the command `cmstp.exe /s /ns C:\Users\ADMINI~W\AppData\Local\Temp\XKNqbpzl.txt` to bypass AppLocker and launch a malicious script.[\[7\]](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html)[\[8\]](https://blog.morphisec.com/cobalt-gang-2.0)[\[9\]](https://researchcenter.paloaltonetworks.com/2018/10/unit42-new-techniques-uncover-attribute-cobalt-gang-commodity-builders-infrastructure-revealed/) |
| [MuddyWater](https://attack.mitre.org/groups/G0069) | [MuddyWater](https://attack.mitre.org/groups/G0069) has used CMSTP.exe and a malicious INF to execute its [POWERSTATS](https://attack.mitre.org/software/S0223) payload.[\[10\]](https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html) |

## 检测

使用进程监控来检测和分析CMSTP.exe的执行和参数。通过将最近的CMSTP.exe的活动与之前已知的正常的参数和加载的文件来对比，以发现异常的和潜在的攻击行为。

Sysmon可以帮助检测潜在的CMSTP.exe的滥用。不同的攻击者手法各异，但是以下检测规则可能有用：

* 检测CMSTP.exe加载、执行远程payload的行为。Event 1（Process creation）中ParentImage包含CMSTP.exe或者Event 3（网络链接）中Image包含CMSTP.exe并且DestinationIP是外网的。
* 检测通过自动提升权限的COM接口绕过UAC。Event 10（进程访问）中CallTrace包含CMLUA.dll或者Event 12、13（注册表事件）中TargetObject包含 CMMGR32.exe。同时也可以监视进程创建事件（Sysmon Event 1）中CMSTP对自动提升权限的COM接口（比如 CMSTPLUA \(3E5FC7F9-9A51-4367-9063-A120244FBEC7\) 和 CMLUAUTIL \(3E000D72-A845-4CD9-BD83-80C07C3B881F\).）的调用。

## 参考

1. [Microsoft. \(2009, October 8\). How Connection Manager Works. Retrieved April 11, 2018.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc786431%28v=ws.10%29)
2. [Carr, N. \(2018, January 31\). Here is some early bad cmstp.exe... Retrieved April 11, 2018.](https://twitter.com/ItsReallyNick/status/958789644165894146)
3. [Moe, O. \(2017, August 15\). Research on CMSTP.exe. Retrieved April 11, 2018.](https://msitpros.com/?p=3960)
4. [Tyrer, N. \(2018, January 30\). CMSTP.exe - remote .sct execution applocker bypass. Retrieved April 11, 2018.](https://twitter.com/NickTyrer/status/958450014111633408)
5. [Moe, O. \(2018, March 1\). Ultimate AppLocker Bypass List. Retrieved April 10, 2018.](https://github.com/api0cradle/UltimateAppLockerByPassList)
6. [Seetharaman, N. \(2018, July 7\). Detecting CMSTP-Enabled Code Execution and UAC Bypass With Sysmon.. Retrieved August 6, 2018.](http://www.endurant.io/cmstp/detecting-cmstp-enabled-code-execution-and-uac-bypass-with-sysmon/)
7. [Svajcer, V. \(2018, July 31\). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html)
8. [Gorelik, M. \(2018, October 08\). Cobalt Group 2.0. Retrieved November 5, 2018.](https://blog.morphisec.com/cobalt-gang-2.0)
9. [Unit 42. \(2018, October 25\). New Techniques to Uncover and Attribute Financial actors Commodity Builders and Infrastructure Revealed. Retrieved December 11, 2018.](https://researchcenter.paloaltonetworks.com/2018/10/unit42-new-techniques-uncover-attribute-cobalt-gang-commodity-builders-infrastructure-revealed/)
10. [Singh, S. et al.. \(2018, March 13\). Iranian Threat Group Updates Tactics, Techniques and Procedures in Spear Phishing Campaign. Retrieved April 11, 2018.](https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html)

