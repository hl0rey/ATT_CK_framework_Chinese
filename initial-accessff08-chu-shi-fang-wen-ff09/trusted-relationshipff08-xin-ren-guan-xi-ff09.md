# 信任关系

攻击者可能使用攻击或者其他手法里利用可以解除到目标的其他组织。利用可信的第三方的已有的访问方式，与通过目标标准的直接的访问方式相比，可能前者会不受保护，或者受到较少的保护。

一个组织通常授予第二或者第三方服务提供商比较高的权限，以便于他们管理内部的系统。比如说一些IT服务提供商、安全服务提供商、基础设备提供商（暖通空调、电梯和物理安全）。第三方服务提供者日常的访问可能只限于他所维护的系统，但是他所维护的系统可能和其他系统在同一网络中。另外，他用来访问网络的账号也可能被攻击和利用。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Network Segmentation](https://attack.mitre.org/mitigations/M1030) |  Network segmentation can be used to isolate infrastructure components that do not require broad network access. |
| [User Account Control](https://attack.mitre.org/mitigations/M1052) |  Properly manage accounts and permissions used by parties in trusted relationships to minimize potential abuse by the party and if the party is compromised by an adversary. |



