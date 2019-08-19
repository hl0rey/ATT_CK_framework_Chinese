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

| Name | Description |
| :--- | :--- |
| [APT18](https://attack.mitre.org/groups/G0026) | [APT18](https://attack.mitre.org/groups/G0026) actors leverage legitimate credentials to log into external remote services.[\[2\]](https://www.rsaconference.com/writable/presentations/file_upload/hta-f02-detecting-and-responding-to-advanced-threats-within-exchange-environments.pdf) |
| [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) | [Dragonfly 2.0](https://attack.mitre.org/groups/G0074) used VPNs and Outlook Web Access \(OWA\) to maintain access to victim networks.[\[3\]](https://www.us-cert.gov/ncas/alerts/TA18-074A)[\[4\]](https://www.us-cert.gov/ncas/alerts/TA17-293A) |
| [FIN5](https://attack.mitre.org/groups/G0053) | [FIN5](https://attack.mitre.org/groups/G0053) has used legitimate VPN, Citrix, or VNC credentials to maintain access to a victim environment.[\[5\]](https://www2.fireeye.com/WBNR-Are-you-ready-to-respond.html)[\[6\]](https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?)[\[7\]](https://www.youtube.com/watch?v=fevGZs0EQu8) |
| [Ke3chang](https://attack.mitre.org/groups/G0004) | [Ke3chang](https://attack.mitre.org/groups/G0004) regained access after eviction via the corporate VPN solution with a stolen VPN certificate, which they had extracted from a compromised host.[\[8\]](https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/) |
| [Linux Rabbit](https://attack.mitre.org/software/S0362) | [Linux Rabbit](https://attack.mitre.org/software/S0362) attempts to gain access to the server via SSH.[\[9\]](https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat) |
| [Night Dragon](https://attack.mitre.org/groups/G0014) | [Night Dragon](https://attack.mitre.org/groups/G0014) has used compromised VPN accounts to gain access to victim systems.[\[10\]](https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf) |
| [OilRig](https://attack.mitre.org/groups/G0049) | [OilRig](https://attack.mitre.org/groups/G0049) uses remote services such as VPN, Citrix, or OWA to persist in an environment.[\[11\]](https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east) |
| [Soft Cell](https://attack.mitre.org/groups/G0093) | [Soft Cell](https://attack.mitre.org/groups/G0093) established VPN access into victim environments.[\[12\]](https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers) |
| [TEMP.Veles](https://attack.mitre.org/groups/G0088) | [TEMP.Veles](https://attack.mitre.org/groups/G0088) has used a VPN to persist in the victim environment.[\[13\]](https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html) |
| [Threat Group-3390](https://attack.mitre.org/groups/G0027) | [Threat Group-3390](https://attack.mitre.org/groups/G0027) actors look for and use VPN profiles during an operation to access the network using external VPN services.[\[14\]](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage) |

## 检测

遵循最佳实践来检测攻击者使用合法账户的访问，收集访问日志，分析不正常的访问模型、活动窗口以及外出办公的时间。

## 参考

1. [Adair, S. \(2015, October 7\). Virtual Private Keylogging: Cisco Web VPNs Leveraged for Access and Persistence. Retrieved March 20, 2017.](https://www.volexity.com/blog/2015/10/07/virtual-private-keylogging-cisco-web-vpns-leveraged-for-access-and-persistence/)

2. [Adair, S. \(2017, February 17\). Detecting and Responding to Advanced Threats within Exchange Environments. Retrieved March 20, 2017.](https://www.rsaconference.com/writable/presentations/file_upload/hta-f02-detecting-and-responding-to-advanced-threats-within-exchange-environments.pdf)
3. [US-CERT. \(2018, March 16\). Alert \(TA18-074A\): Russian Government Cyber Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved June 6, 2018.](https://www.us-cert.gov/ncas/alerts/TA18-074A)
4. [US-CERT. \(2017, October 20\). Alert \(TA17-293A\): Advanced Persistent Threat Activity Targeting Energy and Other Critical Infrastructure Sectors. Retrieved November 2, 2017.](https://www.us-cert.gov/ncas/alerts/TA17-293A)
5. [Scavella, T. and Rifki, A. \(2017, July 20\). Are you Ready to Respond? \(Webinar\). Retrieved October 4, 2017.](https://www2.fireeye.com/WBNR-Are-you-ready-to-respond.html)
6. [Higgins, K. \(2015, October 13\). Prolific Cybercrime Gang Favors Legit Login Credentials. Retrieved October 4, 2017.](https://www.darkreading.com/analytics/prolific-cybercrime-gang-favors-legit-login-credentials/d/d-id/1322645?)
7. [Bromiley, M. and Lewis, P. \(2016, October 7\). Attacking the Hospitality and Gaming Industries: Tracking an Attacker Around the World in 7 Years. Retrieved October 6, 2017.](https://www.youtube.com/watch?v=fevGZs0EQu8)
8. [Smallridge, R. \(2018, March 10\). APT15 is alive and strong: An analysis of RoyalCli and RoyalDNS. Retrieved April 4, 2018.](https://www.nccgroup.trust/uk/about-us/newsroom-and-events/blogs/2018/march/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/)
9. [Anomali Labs. \(2018, December 6\). Pulling Linux Rabbit/Rabbot Malware Out of a Hat. Retrieved March 4, 2019.](https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat)
10. [McAfee® Foundstone® Professional Services and McAfee Labs™. \(2011, February 10\). Global Energy Cyberattacks: “Night Dragon”. Retrieved February 19, 2018.](https://securingtomorrow.mcafee.com/wp-content/uploads/2011/02/McAfee_NightDragon_wp_draft_to_customersv1-1.pdf)
11. [Davis, S. and Caban, D. \(2017, December 19\). APT34 - New Targeted Attack in the Middle East. Retrieved December 20, 2017.](https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east)
12. [Cybereason Nocturnus. \(2019, June 25\). Operation Soft Cell: A Worldwide Campaign Against Telecommunications Providers. Retrieved July 18, 2019.](https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers)
13. [Miller, S, et al. \(2019, April 10\). TRITON Actor TTP Profile, Custom Attack Tools, Detections, and ATT&CK Mapping. Retrieved April 16, 2019.](https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html)
14. [Dell SecureWorks Counter Threat Unit Threat Intelligence. \(2015, August 5\). Threat Group-3390 Targets Organizations for Cyberespionage. Retrieved August 18, 2018.](https://www.secureworks.com/research/threat-group-3390-targets-organizations-for-cyberespionage)



