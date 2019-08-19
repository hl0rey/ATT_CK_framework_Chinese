# 对外开放的远程访问服务

远程访问服务（例如VPN、Citrix或者其他访问机制）允许用户从外部访问企业内部网络资源。通常有远程服务网关管理这些连接和身份验证。像Windows Remote Managerment这样的服务也会被用于远程访问。

攻击者可以将远程访问服务用作对一个网络的初始访问或者持久驻留。通常需要一个访问远程访问服务的合法账户，这可以通过凭据嫁接（诱导或者伪造服务让用户输入合法的账户），或者通过拿下目标网络之后再去获取。对远程访问服务的访问可以作为渗透期间的冗余访问（比如跳板机下线了，可以用远程服务再次接入目标内网）。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Disable or Remove Feature or Program](https://attack.mitre.org/mitigations/M1042) | Disable or block remotely available services that may be unnecessary. |
| [Limit Access to Resource Over Network](https://attack.mitre.org/mitigations/M1035) | Limit access to remote services through centrally managed concentrators such as VPNs and other managed remote access systems. |
| [Multi factor Authentication](https://attack.mitre.org/mitigations/M1032) | Use strong two-factor or multi-factor authentication for remote service accounts to mitigate an adversary's ability to leverage stolen credentials, but be aware of [Two-Factor Authentication Interception](https://attack.mitre.org/techniques/T1111) techniques for some two-factor authentication implementations. |
| [Network Segmentation](https://attack.mitre.org/mitigations/M1030) | Deny direct remote access to internal systems through the use of network proxies, gateways, and firewalls. |

## 例子

## 检测

遵循最佳实践来检测攻击者使用合法账户的访问，收集访问日志，分析不正常的访问模型、活动窗口以及外出办公的时间。

## 参考



