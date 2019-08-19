# 通过可移动媒介复制

攻击者可能直接走到系统内部，目标可能是断网机或者物理隔离的机器，通过可移动媒介将恶意软件复制到目标机器上（利用当媒介插入电脑即自动运行某程序的功能）。如果是为了横向移动，攻击者可能会更改可移动媒介中的文件或者拷贝恶意文件进去，将其重命名为一个合法的文件的命名，来欺骗用户在一个独立的机器上运行。如果是为了初始访问，攻击者可能会手工操作可以的媒介，修改格式化该媒介的系统、或者修改该媒介的固件。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Disable or Remove Feature or Program](https://attack.mitre.org/mitigations/M1042) | Disable Autorun if it is unnecessary. Disallow or restrict removable media at an organizational policy level if it is not required for business operations.[\[14\]](https://support.microsoft.com/en-us/kb/967715)[\[15\]](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx) |
| [Limit Hardware Installation](https://attack.mitre.org/mitigations/M1034) | Limit the use of USB devices and removable media within a network. |

## 例子

| Name | Description |
| :--- | :--- |
| [Agent.btz](https://attack.mitre.org/software/S0092) | [Agent.btz](https://attack.mitre.org/software/S0092) drops itself onto removable media devices and creates an autorun.inf file with an instruction to run that file. When the device is inserted into another system, it opens autorun.inf and loads the malware.[\[1\]](http://blog.threatexpert.com/2008/11/agentbtz-threat-that-hit-pentagon.html) |
| [APT28](https://attack.mitre.org/groups/G0007) | [APT28](https://attack.mitre.org/groups/G0007) uses a tool to infect connected USB devices and transmit itself to air-gapped computers when the infected USB device is inserted.[\[2\]](http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf) |
| [CHOPSTICK](https://attack.mitre.org/software/S0023) | Part of [APT28](https://attack.mitre.org/groups/G0007)'s operation involved using [CHOPSTICK](https://attack.mitre.org/software/S0023) modules to copy itself to air-gapped machines and using files written to USB sticks to transfer data and command traffic.[\[3\]](https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf)[\[2\]](http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf) |
| [Darkhotel](https://attack.mitre.org/groups/G0012) | [Darkhotel](https://attack.mitre.org/groups/G0012)'s selective infector modifies executables stored on removable media as a method of spreading across computers.[\[4\]](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf) |
| [DustySky](https://attack.mitre.org/software/S0062) | [DustySky](https://attack.mitre.org/software/S0062) searches for removable media and duplicates itself onto it.[\[5\]](https://www.clearskysec.com/wp-content/uploads/2016/01/Operation DustySky_TLP_WHITE.pdf) |
| [Flame](https://attack.mitre.org/software/S0143) | [Flame](https://attack.mitre.org/software/S0143) contains modules to infect USB sticks and spread laterally to other Windows systems the stick is plugged into using Autorun functionality.[\[6\]](https://securelist.com/the-flame-questions-and-answers-51/34344/) |
| [H1N1](https://attack.mitre.org/software/S0132) | [H1N1](https://attack.mitre.org/software/S0132) has functionality to copy itself to removable media.[\[7\]](http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2) |
| [njRAT](https://attack.mitre.org/software/S0385) | [njRAT](https://attack.mitre.org/software/S0385) can be configured to spread via removable drives.[\[8\]](https://www.threatminer.org/_reports/2013/fta-1009---njrat-uncovered-1.pdf) |
| [SHIPSHAPE](https://attack.mitre.org/software/S0028) | [APT30](https://attack.mitre.org/groups/G0013) may have used the [SHIPSHAPE](https://attack.mitre.org/software/S0028) malware to move onto air-gapped networks. [SHIPSHAPE](https://attack.mitre.org/software/S0028) targets removable drives to spread to other systems by modifying the drive to use Autorun to execute or by hiding legitimate document files and copying an executable to the folder with the same name as the legitimate document.[\[9\]](https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf) |
| [Unknown Logger](https://attack.mitre.org/software/S0130) | [Unknown Logger](https://attack.mitre.org/software/S0130) is capable of spreading to USB devices.[\[10\]](https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf) |
| [Ursnif](https://attack.mitre.org/software/S0386) | [Ursnif](https://attack.mitre.org/software/S0386) has copied itself to and infected removable drives for propagation.[\[11\]](https://blog.trendmicro.com/trendlabs-security-intelligence/ursnif-the-multifaceted-malware/?_ga=2.165628854.808042651.1508120821-744063452.1505819992)[\[12\]](https://blog.trendmicro.com/trendlabs-security-intelligence/info-stealing-file-infector-hits-us-uk/) |
| [USBStealer](https://attack.mitre.org/software/S0136) | [USBStealer](https://attack.mitre.org/software/S0136) drops itself onto removable media and relies on Autorun to execute the malicious file when a user opens the removable media on another system.[\[13\]](http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/) |

## 检测

监控可移动媒介上的文件访问。检测从可移动媒介挂载或者某人访问之后开始执行的进程。如果远程控制工具用这种方式进行横向移动，那么其他行为就会在它执行之后出现，比如打开用于远程控制的网络连接和网络发现。

## 参考

1. [Shevchenko, S.. \(2008, November 30\). Agent.btz - A Threat That Hit Pentagon. Retrieved April 8, 2016.](http://blog.threatexpert.com/2008/11/agentbtz-threat-that-hit-pentagon.html)

2. [Anthe, C. et al. \(2015, October 19\). Microsoft Security Intelligence Report Volume 19. Retrieved December 23, 2015.](http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf)

3. [FireEye. \(2015\). APT28: A WINDOW INTO RUSSIA’S CYBER ESPIONAGE OPERATIONS?. Retrieved August 19, 2015.](https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf)
4. [Kaspersky Lab's Global Research and Analysis Team. \(2014, November\). The Darkhotel APT A Story of Unusual Hospitality. Retrieved November 12, 2014.](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf)
5. [ClearSky. \(2016, January 7\). Operation DustySky. Retrieved January 8, 2016.](https://www.clearskysec.com/wp-content/uploads/2016/01/Operation DustySky_TLP_WHITE.pdf)
6. [Gostev, A. \(2012, May 28\). The Flame: Questions and Answers. Retrieved March 1, 2017.](https://securelist.com/the-flame-questions-and-answers-51/34344/)
7. [Reynolds, J.. \(2016, September 14\). H1N1: Technical analysis reveals new capabilities – part 2. Retrieved September 26, 2016.](http://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2)
8. [Fidelis Cybersecurity. \(2013, June 28\). Fidelis Threat Advisory \#1009: "njRAT" Uncovered. Retrieved June 4, 2019.](https://www.threatminer.org/_reports/2013/fta-1009---njrat-uncovered-1.pdf)
9. [FireEye Labs. \(2015, April\). APT30 AND THE MECHANICS OF A LONG-RUNNING CYBER ESPIONAGE OPERATION. Retrieved May 1, 2015.](https://www2.fireeye.com/rs/fireye/images/rpt-apt30.pdf)
10. [Settle, A., et al. \(2016, August 8\). MONSOON - Analysis Of An APT Campaign. Retrieved September 22, 2016.](https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf)
11. [Caragay, R. \(2015, March 26\). URSNIF: The Multifaceted Malware. Retrieved June 5, 2019.](https://blog.trendmicro.com/trendlabs-security-intelligence/ursnif-the-multifaceted-malware/?_ga=2.165628854.808042651.1508120821-744063452.1505819992)
12. [Caragay, R. \(2014, December 11\). Info-Stealing File Infector Hits US, UK. Retrieved June 5, 2019.](https://blog.trendmicro.com/trendlabs-security-intelligence/info-stealing-file-infector-hits-us-uk/)
13. [Calvet, J. \(2014, November 11\). Sednit Espionage Group Attacking Air-Gapped Networks. Retrieved January 4, 2017.](http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/)
14. [Microsoft. \(n.d.\). How to disable the Autorun functionality in Windows. Retrieved April 20, 2016.](https://support.microsoft.com/en-us/kb/967715)
15. [Microsoft. \(2007, August 31\). https://technet.microsoft.com/en-us/library/cc771759\(v=ws.10\).aspx. Retrieved April 20, 2016.](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx)



