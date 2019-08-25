# 编译好的HTML文件

编译好的HTML文件（.chm）通常作为微软的HTML帮助系统的一部分发布。CHM文件是HTML、图片、脚本或者其他web相关的编程语言（VBA、JScript、Java、ActiveX）压缩编译而成的。CHM的内容是有HTML帮助执行程序（hh.exe）利用IE渲染展示的。

攻击者可能利用这种技术隐藏恶意代码。通过自定义的CHM文件嵌入payload的方式，可以将payload传送到用户机器上，然后通过用户执行手段触发。CHM文件执行手法可能会绕过应用程序白名单在一些老的、没有打补丁的不需要通过hh.exe执行二进制程序的系统上。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Execution Prevention](https://attack.mitre.org/mitigations/M1038) | Consider using application whitelisting to prevent execution of hh.exe if it is not required for a given system or network to prevent potential misuse by adversaries. |
| [Restrict Web Based Content](https://attack.mitre.org/mitigations/M1021) | Consider blocking download/transfer and execution of potentially uncommon file types known to be used in adversary campaigns, such as CHM files. |

## 例子

| Name | Description |
| :--- | :--- |
| [Astaroth](https://attack.mitre.org/software/S0373) | [Astaroth](https://attack.mitre.org/software/S0373) uses ActiveX objects for file execution and manipulation.[\[6\]](https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/) |
| [Dark Caracal](https://attack.mitre.org/groups/G0070) | [Dark Caracal](https://attack.mitre.org/groups/G0070) leveraged a compiled HTML file that contained a command to download and run an executable.[\[7\]](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf) |
| [Lazarus Group](https://attack.mitre.org/groups/G0032) | [Lazarus Group](https://attack.mitre.org/groups/G0032) has used CHM files to move concealed payloads as part of.[\[8\]](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180244/Lazarus_Under_The_Hood_PDF_final.pdf) |
| [OilRig](https://attack.mitre.org/groups/G0049) | [OilRig](https://attack.mitre.org/groups/G0049) has used a CHM payload to load and execute another malicious file once delivered to a victim.[\[9\]](http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/) |
| [Silence](https://attack.mitre.org/groups/G0091) | [Silence](https://attack.mitre.org/groups/G0091) has weaponized CHM files in their phishing campaigns.[\[10\]](https://cyberforensicator.com/2019/01/20/silence-dissecting-malicious-chm-files-and-performing-forensic-analysis/)[\[11\]](https://securelist.com/the-silence/83009/) |

## 检测

监控和分析hh.exe的执行以及其参数。对比最近对hh.exe正常调用的好的参数，以发现潜在的、可能的攻击活动（比如 混淆、恶意命令）。非标准的进程执行树也可能表示可以和恶意的行为。比如hh.exe是其他可疑进程和攻击技术相关进程的父进程。（比如cmstp.exe regsrv32）

检测CHM文件的存在和使用，特别是通常不使用CHM文件的环境。

## 参考

1. [Microsoft. \(2018, May 30\). Microsoft HTML Help 1.4. Retrieved October 3, 2018.](https://docs.microsoft.com/previous-versions/windows/desktop/htmlhelp/microsoft-html-help-1-4-sdk)

2. [Microsoft. \(n.d.\). HTML Help ActiveX Control Overview. Retrieved October 3, 2018.](https://msdn.microsoft.com/windows/desktop/ms644670)

3. [Microsoft. \(n.d.\). About the HTML Help Executable Program. Retrieved October 3, 2018.](https://msdn.microsoft.com/windows/desktop/ms524405)

4. [Moe, O. \(2017, August 13\). Bypassing Device guard UMCI using CHM – CVE-2017-8625. Retrieved October 3, 2018.](https://msitpros.com/?p=3909)
5. [Microsoft. \(2017, August 8\). CVE-2017-8625 - Internet Explorer Security Feature Bypass Vulnerability. Retrieved October 3, 2018.](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2017-8625)
6. [Doaty, J., Garrett, P.. \(2018, September 10\). We’re Seeing a Resurgence of the Demonic Astaroth WMIC Trojan. Retrieved April 17, 2019.](https://cofense.com/seeing-resurgence-demonic-astaroth-wmic-trojan/)
7. [Blaich, A., et al. \(2018, January 18\). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf)
8. [GReAT. \(2017, April 3\). Lazarus Under the Hood. Retrieved October 3, 2018.](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07180244/Lazarus_Under_The_Hood_PDF_final.pdf)
9. [Falcone, R. and Lee, B.. \(2016, May 26\). The OilRig Campaign: Attacks on Saudi Arabian Organizations Deliver Helminth Backdoor. Retrieved May 3, 2017.](http://researchcenter.paloaltonetworks.com/2016/05/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)
10. [Skulkin, O.. \(2019, January 20\). Silence: Dissecting Malicious CHM Files and Performing Forensic Analysis. Retrieved May 24, 2019.](https://cyberforensicator.com/2019/01/20/silence-dissecting-malicious-chm-files-and-performing-forensic-analysis/)
11. [GReAT. \(2017, November 1\). Silence – a new Trojan attacking financial organizations. Retrieved May 24, 2019.](https://securelist.com/the-silence/83009/)



