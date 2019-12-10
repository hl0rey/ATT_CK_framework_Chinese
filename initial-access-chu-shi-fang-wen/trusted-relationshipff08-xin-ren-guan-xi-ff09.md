# Trusted Relationship（信任关系）

攻击者可能使用攻击或者其他手法里利用可以解除到目标的其他组织。利用可信的第三方的已有的访问方式，与通过目标标准的直接的访问方式相比，可能前者会不受保护，或者受到较少的保护。

一个组织通常授予第二或者第三方服务提供商比较高的权限，以便于他们管理内部的系统。比如说一些IT服务提供商、安全服务提供商、基础设备提供商（暖通空调、电梯和物理安全）。第三方服务提供者日常的访问可能只限于他所维护的系统，但是他所维护的系统可能和其他系统在同一网络中。另外，他用来访问网络的账号也可能被攻击和利用。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Network Segmentation](https://attack.mitre.org/mitigations/M1030) | Network segmentation can be used to isolate infrastructure components that do not require broad network access. |
| [User Account Control](https://attack.mitre.org/mitigations/M1052) | Properly manage accounts and permissions used by parties in trusted relationships to minimize potential abuse by the party and if the party is compromised by an adversary. |

## 例子

| Name | Description |
| :--- | :--- |
| [APT28](https://attack.mitre.org/groups/G0007) | Once [APT28](https://attack.mitre.org/groups/G0007) gained access to the DCCC network, the group then proceeded to use that access to compromise the DNC network.[\[1\]](https://www.justice.gov/file/1080281/download) |
| [menuPass](https://attack.mitre.org/groups/G0045) | [menuPass](https://attack.mitre.org/groups/G0045) has used legitimate access granted to Managed Service Providers in order to access victims of interest.[\[2\]](https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf)[\[3\]](https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html) |

## 检测

为第二和第三方服务提供商以及其他服务提供商对网络的访问的建立监控。如果可信关系是基于IT服务的，那么攻击者可能很快就能对目标采取行动。所以检测凭据访问、横向移动和信息收集行为非常必要。

## 参考

1. [Mueller, R. \(2018, July 13\). Indictment - United States of America vs. VIKTOR BORISOVICH NETYKSHO, et al. Retrieved September 13, 2018.](https://www.justice.gov/file/1080281/download)
2. [PwC and BAE Systems. \(2017, April\). Operation Cloud Hopper: Technical Annex. Retrieved April 13, 2017.](https://www.pwc.co.uk/cyber-security/pdf/cloud-hopper-annex-b-final.pdf)
3. [FireEye iSIGHT Intelligence. \(2017, April 6\). APT10 \(MenuPass Group\): New Tools, Global Campaign Latest Manifestation of Longstanding Threat. Retrieved June 29, 2017.](https://www.fireeye.com/blog/threat-research/2017/04/apt10_menupass_grou.html)

