# 通过第三方服务进行鱼叉式攻击

通过第三方服务进行的鱼叉式攻击是鱼叉式攻击的一种特殊手法。通过第三方服务进行的鱼叉式攻击不同于其他鱼叉式攻击，他利用第三方来进行攻击，而不是通过企业邮件渠道。

所有的鱼叉攻击都是针对特定人、公司或者团体的电子社会工程学。在这个场景下，攻击者通过各种社交媒体服务、个人电子邮件和其他非目标企业控制的服务。这些的安全策略通常不会像目标企业那样严格。像大多数鱼叉式攻击一样，目的是和目标建立融洽的关系或者通过某种方法令对方感兴趣。攻击者可能会创建虚假的社交账号并且发送可能的工作机会给目标（再比如建个女号，嘤嘤嘤、QAQ什么的）。这样就给了攻击者一个合理的理由去询问目标环境中运行的应用、策略以及软件。攻击者可以通过那些服务发送恶意链接和附件。

一个常见的例子是首先通过社交媒体与目标建立融洽的关系，然后发送用于攻击的内容到目标在工作电脑上使用的个人账户里，这可能会绕过一些工作账户的安全限制，目标也更有可能打开邮件，毕竟内容是目标所期待的。如果payload没有按预期执行，那么攻击者可以继续和目标交流，并进行故障排除，并且找出不能运行的原因，并使其正常执行。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Antivirus/Antimalware](https://attack.mitre.org/mitigations/M1049) | Anti-virus can also automatically quarantine suspicious files. |
| [Restrict Web Based Content](https://attack.mitre.org/mitigations/M1021) | Determine if certain social media sites, personal webmail services, or other service that can be used for spearphishing is necessary for business operations and consider blocking access if activity cannot be monitored well or if it poses a significant risk. |
| [User Training](https://attack.mitre.org/mitigations/M1017) | Users can be trained to identify social engineering techniques and spearphishing emails with malicious links. |

## 例子

| Name | Description |
| :--- | :--- |
| [Dark Caracal](https://attack.mitre.org/groups/G0070) | [Dark Caracal](https://attack.mitre.org/groups/G0070) spearphished victims via Facebook and Whatsapp.[\[1\]](https://info.lookout.com/rs/051-ESQ-475/images/Lookout_Dark-Caracal_srr_20180118_us_v.1.0.pdf) |
| [Magic Hound](https://attack.mitre.org/groups/G0059) | [Magic Hound](https://attack.mitre.org/groups/G0059) used various social media channels to spearphish victims.[\[2\]](https://www.secureworks.com/research/the-curious-case-of-mia-ash) |

## 检测

因为大多数用于鱼叉式攻击的第三方服务都使用SSL/TLS加密，所以需要使用SSL/TSL中间人解密流量进行检测初始通信和交付。使用了SSL/TLS中间人解密流量之后，入侵检测可以检测签名，其他安全网关设备也可以检测恶意软件。

反病毒软件可能检测到下载到用户机器上的恶意文档和程序。端点感知可以在文档打开（比如微软office文档和PDF在打开之后，访问互联网或者启动了powershell.exe）之后检测恶意事件（例如客户端执行手法和脚本）。

