# Spearphishing Link（通过链接鱼叉式攻击）

通过链接鱼叉式攻击是鱼叉式攻击的一种特殊手法。它不同于其他鱼叉式攻击，他将恶意软件包含在邮件内的链接中，而不是直接把恶意文件贴到附件中，这可以用来规避对附件的安全检测。

所有的鱼叉攻击都是针对特定人、公司或者团体的电子社会工程学。在这种场景下，邮件内容中包含有恶意的链接。通常其中的文本内容是为了社会工程学攻击而精心设计的，它会要求用户去点击或者拷贝链接到浏览器中去访问，从而利用用户执行。被访问的网站可能会利用浏览器漏洞攻击用户的浏览器，或者弹出提示框让用户下载应用、文档或者压缩文件，甚至直接让用户下载可执行程序。会让用户干什么完全取决于邮件的内容怎么写。攻击者还可能在邮件中包含可以直接和电子邮件阅读器交互的链接（应该是打开电子邮件就会被加载的资源），一般是直接利用终端系统漏洞或者检测邮件是否收到（应该是邮件一旦打开，资源被加载，攻击者即知道邮件被打开了）的嵌入式图像。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Restrict Web Based Content](https://attack.mitre.org/mitigations/M1021) | Determine if certain websites that can be used for spearphishing are necessary for business operations and consider blocking access if activity cannot be monitored well or if it poses a significant risk. |
| [User Training](https://attack.mitre.org/mitigations/M1017) | Users can be trained to identify social engineering techniques and spearphishing emails with malicious links. |

## 例子

| Name | Description |
| :--- | :--- |
| [APT28](https://attack.mitre.org/groups/G0007) | [APT28](https://attack.mitre.org/groups/G0007) sent spearphishing emails which used a URL-shortener service to masquerade as a legitimate service and to redirect targets to credential harvesting sites.[\[1\]](https://www.justice.gov/file/1080281/download)[\[2\]](https://www.welivesecurity.com/2019/05/22/journey-zebrocy-land/) |
| [APT29](https://attack.mitre.org/groups/G0016) | [APT29](https://attack.mitre.org/groups/G0016) has used spearphishing with a link to trick victims into clicking on a link to a zip file containing malicious files.[\[3\]](http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016) |
| [APT32](https://attack.mitre.org/groups/G0050) | [APT32](https://attack.mitre.org/groups/G0050) has sent spearphishing emails containing malicious links.[\[4\]](https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/)[\[5\]](https://www.cybereason.com/blog/operation-cobalt-kitty-apt) |
| [APT33](https://attack.mitre.org/groups/G0064) | [APT33](https://attack.mitre.org/groups/G0064) has sent spearphishing emails containing links to .hta files.[\[6\]](https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html)[\[7\]](https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage) |
| [APT39](https://attack.mitre.org/groups/G0087) | [APT39](https://attack.mitre.org/groups/G0087) leveraged spearphishing emails with malicious links to initially compromise victims.[\[8\]](https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html) |
| [Cobalt Group](https://attack.mitre.org/groups/G0080) | [Cobalt Group](https://attack.mitre.org/groups/G0080) has sent emails with URLs pointing to malicious documents.[\[9\]](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html) |
| [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) | [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) used spearphishing with PDF attachments containing malicious links that redirected to credential harvesting websites.[\[10\]](https://www.us-cert.gov/ncas/alerts/TA18-074A) |
| [Elderwood](https://attack.mitre.org/groups/G0066) | [Elderwood](https://attack.mitre.org/groups/G0066) has delivered zero-day exploits and malware to victims via targeted emails containing a link to malicious content hosted on an uncommon Web server.[\[11\]](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)[\[12\]](https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China) |
| [Emotet](https://attack.mitre.org/software/S0367) | [Emotet](https://attack.mitre.org/software/S0367) has been delivered by phishing emails containing links.[\[13\]](https://blog.trendmicro.com/trendlabs-security-intelligence/new-banking-malware-uses-network-sniffing-for-data-theft/)[\[14\]](https://securelist.com/the-banking-trojan-emotet-detailed-analysis/69560/)[\[15\]](https://www.cisecurity.org/blog/emotet-changes-ttp-and-arrives-in-united-states/)[\[16\]](https://support.malwarebytes.com/docs/DOC-2295)[\[17\]](https://www.symantec.com/blogs/threat-intelligence/evolution-emotet-trojan-distributor)[\[18\]](https://www.us-cert.gov/ncas/alerts/TA18-201A)[\[19\]](https://blog.talosintelligence.com/2019/01/return-of-emotet.html)[\[19\]](https://blog.talosintelligence.com/2019/01/return-of-emotet.html)[\[20\]](https://www.picussecurity.com/blog/the-christmas-card-you-never-wanted-a-new-wave-of-emotet-is-back-to-wreak-havoc.html) |
| [FIN4](https://attack.mitre.org/groups/G0085) | [FIN4](https://attack.mitre.org/groups/G0085) has used spearphishing emails \(often sent from compromised accounts\) containing malicious links.[\[21\]](https://www.fireeye.com/current-threats/threat-intelligence-reports/rpt-fin4.html)[\[22\]](https://www2.fireeye.com/WBNR-14Q4NAMFIN4.html) |
| [FIN8](https://attack.mitre.org/groups/G0061) | [FIN8](https://attack.mitre.org/groups/G0061) has distributed targeted emails containing links to malicious documents with embedded macros.[\[23\]](https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html) |
| [Leviathan](https://attack.mitre.org/groups/G0065) | [Leviathan](https://attack.mitre.org/groups/G0065) has sent spearphishing emails with links, often using a fraudulent lookalike domain and stolen branding.[\[24\]](https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets) |
| [Magic Hound](https://attack.mitre.org/groups/G0059) | [Magic Hound](https://attack.mitre.org/groups/G0059) sent shortened URL links over email to victims. The URLs linked to Word documents with malicious macros that execute PowerShells scripts to download Pupy.[\[25\]](https://www.secureworks.com/research/the-curious-case-of-mia-ash) |
| [Night Dragon](https://attack.mitre.org/groups/G0014) | [Night Dragon](https://attack.mitre.org/groups/G0014) sent spearphishing emails containing links to compromised websites where malware was downloaded.[\[26\]](https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf) |
| [OilRig](https://attack.mitre.org/groups/G0049) | [OilRig](https://attack.mitre.org/groups/G0049) has sent spearphising emails with malicious links to potential victims.[\[27\]](https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/) |
| [Patchwork](https://attack.mitre.org/groups/G0040) | [Patchwork](https://attack.mitre.org/groups/G0040) has used spearphishing with links to deliver files with exploits to initial victims. The group has used embedded image tags \(known as web bugs\) with unique, per-recipient tracking links in their emails for the purpose of identifying which recipients opened messages.[\[28\]](http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries)[\[29\]](https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf)[\[30\]](https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/) |
| [Stolen Pencil](https://attack.mitre.org/groups/G0086) | [Stolen Pencil](https://attack.mitre.org/groups/G0086) sent spearphishing emails containing links to domains controlled by the threat actor.[\[31\]](https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/) |
| [TA505](https://attack.mitre.org/groups/G0092) | [TA505](https://attack.mitre.org/groups/G0092) has sent spearphishing emails containing malicious links.[\[32\]](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta505-dridex-globeimposter)[\[33\]](https://www.proofpoint.com/us/threat-insight/post/servhelper-and-flawedgrace-new-malware-introduced-ta505) |
| [Turla](https://attack.mitre.org/groups/G0010) | [Turla](https://attack.mitre.org/groups/G0010) attempted to trick targets into clicking on a link featuring a seemingly legitimate domain from Adobe.com to download their malware and gain initial access.[\[34\]](https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf) |

## 检测

可以通过邮件的链接（包括短链接）检测来发现是否访问或者跳转到一个已知的恶意网站。引爆室（引爆室、震爆室应该是一个东西）可以用来检测这些链接是否有潜在的威胁，或者在用户访问它时截获他的内容。

这种攻击技术通常需要在终端上的用户的交互，所以在用户执行之后有很多可以检测钓鱼链接的点。

## 参考

1. [Mueller, R. \(2018, July 13\). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.](https://www.justice.gov/file/1080281/download)
2. [ESET Research. \(2019, May 22\). A journey to Zebrocy land. Retrieved June 20, 2019.](https://www.welivesecurity.com/2019/05/22/journey-zebrocy-land/)
3. [Dunwoody, M. and Carr, N.. \(2016, September 27\). No Easy Breach DerbyCon 2016. Retrieved October 4, 2016.](http://www.slideshare.net/MatthewDunwoody1/no-easy-breach-derby-con-2016)
4. [Foltýn, T. \(2018, March 13\). OceanLotus ships new backdoor using old tricks. Retrieved May 22, 2018.](https://www.welivesecurity.com/2018/03/13/oceanlotus-ships-new-backdoor/)
5. [Dahan, A. \(2017, May 24\). OPERATION COBALT KITTY: A LARGE-SCALE APT IN ASIA CARRIED OUT BY THE OCEANLOTUS GROUP. Retrieved November 5, 2018.](https://www.cybereason.com/blog/operation-cobalt-kitty-apt)
6. [O'Leary, J., et al. \(2017, September 20\). Insights into Iranian Cyber Espionage: APT33 Targets Aerospace and Energy Sectors and has Ties to Destructive Malware. Retrieved February 15, 2018.](https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html)
7. [Security Response attack Investigation Team. \(2019, March 27\). Elfin: Relentless Espionage Group Targets Multiple Organizations in Saudi Arabia and U.S.. Retrieved April 10, 2019.](https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage)
8. [Hawley et al. \(2019, January 29\). APT39: An Iranian Cyber Espionage Group Focused on Personal Information. Retrieved February 19, 2019.](https://www.fireeye.com/blog/threat-research/2019/01/apt39-iranian-cyber-espionage-group-focused-on-personal-information.html)
9. [Svajcer, V. \(2018, July 31\). Multiple Cobalt Personality Disorder. Retrieved September 5, 2018.](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html)
10. [US-CERT. \(2018, March 16\). Alert \(TA18-074A\): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.](https://www.us-cert.gov/ncas/alerts/TA18-074A)
11. [O'Gorman, G., and McDonald, G.. \(2012, September 6\). The Elderwood Project. Retrieved February 15, 2018.](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)
12. [Clayton, M.. \(2012, September 14\). Stealing US business secrets: Experts ID two huge cyber 'gangs' in China. Retrieved February 15, 2018.](https://www.csmonitor.com/USA/2012/0914/Stealing-US-business-secrets-Experts-ID-two-huge-cyber-gangs-in-China)
13. [Salvio, J.. \(2014, June 27\). New Banking Malware Uses Network Sniffing for Data Theft. Retrieved March 25, 2019.](https://blog.trendmicro.com/trendlabs-security-intelligence/new-banking-malware-uses-network-sniffing-for-data-theft/)
14. [Shulmin, A. . \(2015, April 9\). The Banking Trojan Emotet: Detailed Analysis. Retrieved March 25, 2019.](https://securelist.com/the-banking-trojan-emotet-detailed-analysis/69560/)
15. [CIS. \(2017, April 28\). Emotet Changes TTPs and Arrives in United States. Retrieved January 17, 2019.](https://www.cisecurity.org/blog/emotet-changes-ttp-and-arrives-in-united-states/)
16. [Smith, A.. \(2017, December 22\). Protect your network from Emotet Trojan with Malwarebytes Endpoint Security. Retrieved January 17, 2019.](https://support.malwarebytes.com/docs/DOC-2295)
17. [Symantec. \(2018, July 18\). The Evolution of Emotet: From Banking Trojan to Threat Distributor. Retrieved March 25, 2019.](https://www.symantec.com/blogs/threat-intelligence/evolution-emotet-trojan-distributor)
18. [US-CERT. \(2018, July 20\). Alert \(TA18-201A\) Emotet Malware. Retrieved March 25, 2019.](https://www.us-cert.gov/ncas/alerts/TA18-201A)
19. [Brumaghin, E.. \(2019, January 15\). Emotet re-emerges after the holidays. Retrieved March 25, 2019.](https://blog.talosintelligence.com/2019/01/return-of-emotet.html)
20. [Özarslan, S. \(2018, December 21\). The Christmas Card you never wanted - A new wave of Emotet is back to wreak havoc. Retrieved March 25, 2019.](https://www.picussecurity.com/blog/the-christmas-card-you-never-wanted-a-new-wave-of-emotet-is-back-to-wreak-havoc.html)
21. [Vengerik, B. et al.. \(2014, December 5\). Hacking the Street? FIN4 Likely Playing the Market. Retrieved December 17, 2018.](https://www.fireeye.com/current-threats/threat-intelligence-reports/rpt-fin4.html)
22. [Vengerik, B. & Dennesen, K.. \(2014, December 5\). Hacking the Street? FIN4 Likely Playing the Market. Retrieved January 15, 2019.](https://www2.fireeye.com/WBNR-14Q4NAMFIN4.html)
23. [Elovitz, S. & Ahl, I. \(2016, August 18\). Know Your Enemy: New Financially-Motivated & Spear-Phishing Group. Retrieved February 26, 2018.](https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html)
24. [Axel F, Pierre T. \(2017, October 16\). Leviathan: Espionage actor spearphishes maritime and defense targets. Retrieved February 15, 2018.](https://www.proofpoint.com/us/threat-insight/post/leviathan-espionage-actor-spearphishes-maritime-and-defense-targets)
25. [Counter Threat Unit Research Team. \(2017, July 27\). The Curious Case of Mia Ash: Fake Persona Lures Middle Eastern Targets. Retrieved February 26, 2018.](https://www.secureworks.com/research/the-curious-case-of-mia-ash)
26. [McAfee® Foundstone® Professional Services and McAfee Labs™. \(2011, February 10\). Global Energy Cyberattacks: “Night Dragon”. Retrieved February 19, 2018.](https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf)
27. [Lee, B., Falcone, R. \(2018, February 23\). OopsIE! OilRig Uses ThreeDollars to Deliver New Trojan. Retrieved July 16, 2018.](https://researchcenter.paloaltonetworks.com/2018/02/unit42-oopsie-oilrig-uses-threedollars-deliver-new-trojan/)
28. [Hamada, J.. \(2016, July 25\). Patchwork cyberespionage group expands targets from governments to wide range of industries. Retrieved August 17, 2016.](http://www.symantec.com/connect/blogs/patchwork-cyberespionage-group-expands-targets-governments-wide-range-industries)
29. [Lunghi, D., et al. \(2017, December\). Untangling the Patchwork Cyberespionage Group. Retrieved July 10, 2018.](https://documents.trendmicro.com/assets/tech-brief-untangling-the-patchwork-cyberespionage-group.pdf)
30. [Meltzer, M, et al. \(2018, June 07\). Patchwork APT Group Targets US Think Tanks. Retrieved July 16, 2018.](https://www.volexity.com/blog/2018/06/07/patchwork-apt-group-targets-us-think-tanks/)
31. [ASERT team. \(2018, December 5\). STOLEN PENCIL Campaign Targets Academia. Retrieved February 5, 2019.](https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/)
32. [Proofpoint Staff. \(2017, September 27\). Threat Actor Profile: TA505, From Dridex to GlobeImposter. Retrieved May 28, 2019.](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta505-dridex-globeimposter)
33. [Schwarz, D. and Proofpoint Staff. \(2019, January 9\). ServHelper and FlawedGrace - New malware introduced by TA505. Retrieved May 28, 2019.](https://www.proofpoint.com/us/threat-insight/post/servhelper-and-flawedgrace-new-malware-introduced-ta505)
34. [ESET, et al. \(2018, January\). Diplomats in Eastern Europe bitten by a Turla mosquito. Retrieved July 3, 2018.](https://www.welivesecurity.com/wp-content/uploads/2018/01/ESET_Turla_Mosquito.pdf)
35. 
