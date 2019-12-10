# Drive-by Compromise（水坑攻击）

水坑攻击是指攻击者通过用户正常的访问网站的行为来获取目标权限的攻击手法。这种攻击以目标用户的浏览器为攻击或者说是漏洞利用的目标。

有很多把漏洞利用代码发送到目标浏览器的方法，包括以下几种：

* 攻击者拿下一个合法的网站之后，在其网页中注入恶意代码（JavaScript、IFrames、跨站脚本等）。
* 通过合法的广告提供商去散播恶意的广告。
* 任何可以让攻击者显示网页内容，或者在用户机器上执行脚本的的Web程序内置的接口。（论坛发帖、评论或者其他用户可以自定义内容的功能）

通常被攻击者用作水坑的工具的网站是被特定群体访问的，比如政府、特定行业和地区，其中的人是特定的用户、或者因为共同的爱好聚集起来的一群人。这种攻击手法被叫做策略性网络攻击或者水坑攻击。这有几个已知的例子。

## 缓解方法

| Mitigation | Description |
| :--- | :--- |
| [Application Isolation and Sandboxing](https://attack.mitre.org/mitigations/M1048) | Browser sandboxes can be used to mitigate some of the impact of exploitation, but sandbox escapes may still exist.Other types of virtualization and application microsegmentation may also mitigate the impact of client-side exploitation. The risks of additional exploits and weaknesses in implementation may still exist for these types of systems.[\[21\]](https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/)[\[22\]](https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/) |
| [Exploit Protection](https://attack.mitre.org/mitigations/M1050) | Security applications that look for behavior used during exploitation such as Windows Defender Exploit Guard \(WDEG\) and the Enhanced Mitigation Experience Toolkit \(EMET\) can be used to mitigate some exploitation behavior. Control flow integrity checking is another way to potentially identify and stop a software exploit from occurring. Many of these protections depend on the architecture and target application binary for compatibility.[\[23\]](https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/)[\[24\]](https://en.wikipedia.org/wiki/Control-flow_integrity) |
| [Restrict Web Based Content](https://attack.mitre.org/mitigations/M1021) | For malicious code served up through ads, adblockers can help prevent that code from executing in the first place.Script blocking extensions can help prevent the execution of JavaScript that may commonly be used during the exploitation process. |
| [Update Software](https://attack.mitre.org/mitigations/M1051) | Ensure all browsers and plugins kept updated can help prevent the exploit phase of this technique. Use modern browsers with security features turned on.例子 |

## 例子

| Name | Description |
| :--- | :--- |
| [APT19](https://attack.mitre.org/groups/G0073) | [APT19](https://attack.mitre.org/groups/G0073) performed a watering hole attack on forbes.com in 2014 to compromise targets.[\[2\]](https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/) |
| [APT32](https://attack.mitre.org/groups/G0050) | [APT32](https://attack.mitre.org/groups/G0050) has infected victims by tricking them into visiting compromised watering hole websites.[\[3\]](https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/) |
| [APT37](https://attack.mitre.org/groups/G0067) | [APT37](https://attack.mitre.org/groups/G0067) has used strategic web compromises, particularly of South Korean websites, to distribute malware. The group has also used torrent file-sharing sites to more indiscriminately disseminate malware to victims. As part of their compromises, the group has used a Javascript based profiler called RICECURRY to profile a victim's web browser and deliver malicious code accordingly.[\[4\]](https://securelist.com/operation-daybreak/75100/)[\[5\]](https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf) |
| [APT38](https://attack.mitre.org/groups/G0082) | [APT38](https://attack.mitre.org/groups/G0082) has conducted watering holes schemes to gain initial access to victims.[\[6\]](https://content.fireeye.com/apt/rpt-apt38) |
| [BRONZE BUTLER](https://attack.mitre.org/groups/G0060) | [BRONZE BUTLER](https://attack.mitre.org/groups/G0060) compromised three Japanese websites using a Flash exploit to perform watering hole attacks.[\[7\]](https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan) |
| [Dark Caracal](https://attack.mitre.org/groups/G0070) | [Dark Caracal](https://attack.mitre.org/groups/G0070) leveraged a watering hole to serve up malicious code.[\[8\]](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf) |
| [Darkhotel](https://attack.mitre.org/groups/G0012) | [Darkhotel](https://attack.mitre.org/groups/G0012) used embedded iframes on hotel login portals to redirect selected victims to download malware.[\[9\]](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf) |
| [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) | [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) compromised legitimate organizations' websites to create watering holes to compromise victims.[\[10\]](https://www.us-cert.gov/ncas/alerts/TA18-074A) |
| [Elderwood](https://attack.mitre.org/groups/G0066) | [Elderwood](https://attack.mitre.org/groups/G0066) has delivered zero-day exploits and malware to victims by injecting malicious code into specific public Web pages visited by targets within a particular sector.[\[11\]](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)[\[12\]](https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China)[\[13\]](http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html) |
| [KARAE](https://attack.mitre.org/software/S0215) | [KARAE](https://attack.mitre.org/software/S0215) was distributed through torrent file-sharing websites to South Korean victims, using a YouTube video downloader application as a lure.[\[5\]](https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf) |
| [Lazarus Group](https://attack.mitre.org/groups/G0032) | [Lazarus Group](https://attack.mitre.org/groups/G0032) delivered [RATANKBA](https://attack.mitre.org/software/S0241) to victims via a compromised legitimate website.[\[14\]](https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/) |
| [Leafminer](https://attack.mitre.org/groups/G0077) | [Leafminer](https://attack.mitre.org/groups/G0077) has infected victims using watering holes.[\[15\]](https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east) |
| [Patchwork](https://attack.mitre.org/groups/G0040) | [Patchwork](https://attack.mitre.org/groups/G0040) has used watering holes to deliver files with exploits to initial victims.[\[16\]](http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries)[\[17\]](https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/) |
| [PLATINUM](https://attack.mitre.org/groups/G0068) | [PLATINUM](https://attack.mitre.org/groups/G0068) has sometimes used drive-by attacks against vulnerable browser plugins.[\[18\]](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf) |
| [POORAIM](https://attack.mitre.org/software/S0216) | [POORAIM](https://attack.mitre.org/software/S0216) has been delivered through compromised sites acting as watering holes.[\[5\]](https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf) |
| [Threat Group-3390](https://attack.mitre.org/groups/G0027) | [Threat Group-3390](https://attack.mitre.org/groups/G0027) has extensively used strategic web compromises to target victims.[\[19\]](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage)[\[20\]](https://securelist.com/luckymouse-hits-national-data-center/86083/) |

## 检测

防火墙和代理可以检测URL里的可能的已知的恶意域名和参数。他们可以对网站和他们加载的资源做名誉检测，例如这个域名注册多长时间了，这个域名属于谁，如果域名在已知的黑名单上，那么有多少用户曾经连接过它。

网络入侵检测系统有时会有SSL/TLS中间人检查功能（也就是说能解密https的流量），这能够帮助发现已知的恶意脚本（信息收集、堆喷射、浏览器标识脚本经常被重用）、基本的脚本混淆和漏洞利用代码。

检测基于合法网站的水坑攻击可能比较困难。查看用户终端可能会发现成功的水坑攻击，比如浏览器进程的不正常行为。不正常的行为包括可疑的文件写入磁盘、注入进程隐藏执行代码、扫描发现其他机器、或者其他表明攻击者向目标传输了其他工具的行为。

## 参考

1. [Adair, S., Moran, N. \(2012, May 15\). Cyber Espionage & Strategic Web Compromises – Trusted Websites Serving Dangerous Results. Retrieved March 13, 2018.](http://blog.shadowserver.org/2012/05/15/cyber-espionage-strategic-web-compromises-trusted-websites-serving-dangerous-results/)
2. [Grunzweig, J., Lee, B. \(2016, January 22\). New Attacks Linked to C0d0so0 Group. Retrieved August 2, 2018.](https://researchcenter.paloaltonetworks.com/2016/01/new-attacks-linked-to-c0d0s0-group/)
3. [Foltýn, T. \(2018, March 13\). OceanLotus ships new backdoor using old tricks. Retrieved May 22, 2018.](https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/)
4. [Raiu, C., and Ivanov, A. \(2016, June 17\). Operation Daybreak. Retrieved February 15, 2018.](https://securelist.com/operation-daybreak/75100/)
5. [FireEye. \(2018, February 20\). APT37 \(Reaper\): The Overlooked North Korean Actor. Retrieved March 1, 2018.](https://www2.fireeye.com/rs/848-DID-242/images/rpt_APT37.pdf)
6. [FireEye. \(2018, October 03\). APT38: Un-usual Suspects. Retrieved November 6, 2018.](https://content.fireeye.com/apt/rpt-apt38)
7. [DiMaggio, J. \(2016, April 28\). Tick cyberespionage group zeros in on Japan. Retrieved July 16, 2018.](https://www.symantec.com/connect/blogs/tick-cyberespionage-group-zeros-japan)
8. [Blaich, A., et al. \(2018, January 18\). Dark Caracal: Cyber-espionage at a Global Scale. Retrieved April 11, 2018.](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf)
9. [Kaspersky Lab's Global Research and Analysis Team. \(2014, November\). The Darkhotel APT A Story of Unusual Hospitality. Retrieved November 12, 2014.](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08070903/darkhotel_kl_07.11.pdf)
10. [US-CERT. \(2018, March 16\). Alert \(TA18-074A\): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.](https://www.us-cert.gov/ncas/alerts/TA18-074A)
11. [O'Gorman, G., and McDonald, G.. \(2012, September 6\). The Elderwood Project. Retrieved February 15, 2018.](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)
12. [Clayton, M.. \(2012, September 14\). Stealing US business secrets: Experts ID two huge cyber 'gangs' in China. Retrieved February 15, 2018.](https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China)
13. [Paganini, P. \(2012, September 9\). Elderwood project, who is behind Op. Aurora and ongoing attacks?. Retrieved February 13, 2018.](http://securityaffairs.co/wordpress/8528/hacking/elderwood-project-who-is-behind-op-aurora-and-ongoing-attacks.html)
14. [Trend Micro. \(2017, February 27\). RATANKBA: Delving into Large-scale Watering Holes against Enterprises. Retrieved May 22, 2018.](https://blog.trendmicro.com/trendlabs-security-intelligence/ratankba-watering-holes-against-enterprises/)
15. [Symantec Security Response. \(2018, July 25\). Leafminer: New Espionage Campaigns Targeting Middle Eastern Regions. Retrieved August 28, 2018.](https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east)
16. [Hamada, J.. \(2016, July 25\). Patchwork cyberespionage group expands targets from governments to wide range of industries. Retrieved August 17, 2016.](http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries)
17. [Meltzer, M, et al. \(2018, June 07\). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.](https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/)
18. [Windows Defender Advanced Threat Hunting Team. \(2016, April 29\). PLATINUM: Targeted attacks in South and Southeast Asia. Retrieved February 15, 2018.](https://download.microsoft.com/download/2/2/5/225BFE3E-E1DE-4F5B-A77B-71200928D209/Platinum%20feature%20article%20-%20Targeted%20attacks%20in%20South%20and%20Southeast%20Asia%20April%202016.pdf)
19. [Dell SecureWorks Counter Threat Unit Threat Intelligence. \(2015, August 5\). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage)
20. [Legezo, D. \(2018, June 13\). LuckyMouse hits national data center to organize country-level waterholing campaign. Retrieved August 18, 2018.](https://securelist.com/luckymouse-hits-national-data-center/86083/)
21. [Cowan, C. \(2017, March 23\). Strengthening the Microsoft Edge Sandbox. Retrieved March 12, 2018.](https://blogs.windows.com/msedgedev/2017/03/23/strengthening-microsoft-edge-sandbox/)
22. [Goodin, D. \(2017, March 17\). Virtual machine escape fetches $105,000 at Pwn2Own hacking contest - updated. Retrieved March 12, 2018.](https://arstechnica.com/information-technology/2017/03/hack-that-escapes-vm-by-exploiting-edge-browser-fetches-105000-at-pwn2own/)
23. [Nunez, N. \(2017, August 9\). Moving Beyond EMET II – Windows Defender Exploit Guard. Retrieved March 12, 2018.](https://blogs.technet.microsoft.com/srd/2017/08/09/moving-beyond-emet-ii-windows-defender-exploit-guard/)
24. [Wikipedia. \(2018, January 11\). Control-flow integrity. Retrieved March 12, 2018.](https://en.wikipedia.org/wiki/Control-flow_integrity)

