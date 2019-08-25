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

## 参考





