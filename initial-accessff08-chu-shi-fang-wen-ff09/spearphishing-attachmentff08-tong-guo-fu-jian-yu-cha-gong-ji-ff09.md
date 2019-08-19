# 通过附件鱼叉攻击

通过附件的鱼叉攻击是鱼叉攻击的一种变体。通过附件进行的鱼叉攻击不同于其他类型的鱼叉攻击，它将恶意软件附在邮件附件里。所有的鱼叉攻击都是针对特定人、公司或者团体的电子社会工程学。在这种场景中，攻击者将恶意文件放到邮件的附件中并且靠用户打开该文件来获得代码执行。

有多种文件可以作为附件，比如微软的office文档、可执行文件、PDF或者压缩包。在打开附件（或者点击确定，过掉安全防护）之后，攻击者将利用目标系统的漏洞，或者直接在目标系统执行执行程序。邮件正文通常给出一个看似可信的理由来说明附件为什么必须被打开，也许也会介绍怎么绕过安全软件的防护。有时邮件里也会包含解密压缩包的密码，这是为了绕过电子邮件防御网关。通常攻击者会更改后缀名和图标让一个可执行文件看起来像一个文档，或者让这个文件像其他的文件。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Antivirus/Antimalware](https://attack.mitre.org/mitigations/M1049) | Anti-virus can also automatically quarantine suspicious files. |
| [Network Intrusion Prevention](https://attack.mitre.org/mitigations/M1031) | Network intrusion prevention systems and systems designed to scan and remove malicious email attachments can be used to block activity. |
| [Restrict Web Based Content](https://attack.mitre.org/mitigations/M1021) | Block unknown or unused attachments by default that should not be transmitted over email as a best practice to prevent some vectors, such as .scr, .exe, .pif, .cpl, etc. Some email scanning devices can open and analyze compressed and encrypted formats, such as zip and rar that may be used to conceal malicious attachments in [Obfuscated Files or Information](https://attack.mitre.org/techniques/T1027). |
| [User Training](https://attack.mitre.org/mitigations/M1017) | Users can be trained to identify social engineering techniques and spearphishing emails. |

## 例子





