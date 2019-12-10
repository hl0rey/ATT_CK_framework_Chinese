# Supply Chain Compromise（供应链攻击）

供应链攻击是为了攻击目标系统或获取数据而在最终客户收到产品之前对产品进行的操作。

供应链攻击可能发生在以下的任何一个阶段：

* 对开发工具进行操作
* 对开发环境进行操作
* 对代码库（公开的或者私有的）进行操作
* 对产品依赖的开源代码库进行操作
* 对软件的更新包或者发行版进行操作
* 攻击或者感染系统镜像（感染还未出厂的可移动磁盘）
* 使用修改过的版本替换合法软件
* 向合法的经销商出售更改过的或者假冒的产品
* 装运封锁（应该是指产品运输阶段）

虽然供应链攻击可能影响硬件或者软件的各个组件，但是攻击者常常着眼于向合法软件的升级和分发渠道添加恶意程序。成为目标的往往是特定的群体，或者在向广泛的大众分发的软件里附件上只针对某些目标生效的策略。流行的开源项目经常作为很多应用的依赖项，所以它经常会成为攻击者间接向目标产品添加恶意代码的目标。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Update Software](https://attack.mitre.org/mitigations/M1051) | A patch management process should be implemented to check unused dependencies, unmaintained and/or previously vulnerable dependencies, unnecessary features, components, files, and documentation. |
| [Vulnerability Scanning](https://attack.mitre.org/mitigations/M1016) | Continuous monitoring of vulnerability sources and the use of automatic and manual code review tools should also be implemented as well. |

## 例子

| Name | Description |
| :--- | :--- |
| [CCBkdr](https://attack.mitre.org/software/S0222) | [CCBkdr](https://attack.mitre.org/software/S0222) was added to a legitimate, signed version 5.33 of the CCleaner software and distributed on CCleaner's distribution site.[\[6\]](http://blog.talosintelligence.com/2017/09/avast-distributes-malware.html)[\[7\]](http://www.intezer.com/evidence-aurora-operation-still-active-supply-chain-attack-through-ccleaner/)[\[1\]](https://blog.avast.com/new-investigations-in-ccleaner-incident-point-to-a-possible-third-stage-that-had-keylogger-capacities) |
| [Elderwood](https://attack.mitre.org/groups/G0066) | [Elderwood](https://attack.mitre.org/groups/G0066) has targeted manufacturers in the supply chain for the defense industry.[\[4\]](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf) |
| [NotPetya](https://attack.mitre.org/software/S0368) | [NotPetya](https://attack.mitre.org/software/S0368)'s initial infection vector for the June 27, 2017 compromise was a backdoor in the Ukrainian tax accounting software M.E.Doc.[\[8\]](https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html)[\[9\]](https://www.us-cert.gov/ncas/alerts/TA17-181A)[\[10\]](https://blog.talosintelligence.com/2017/07/the-medoc-connection.html) |
| [Smoke Loader](https://attack.mitre.org/software/S0226) | [Smoke Loader](https://attack.mitre.org/software/S0226) was distributed through a compromised update to a Tor client with a coin miner payload.[\[2\]](https://cloudblogs.microsoft.com/microsoftsecure/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign/) |

## 检测

对发行版的二进制文件进行hash校验或者其他检查。扫描下载的文件所带的签名，并且在部署应用之前先对应用进行测试，试图发现潜在的威胁。对硬件进行检查，发现可能的篡改。

## 参考

1. [Avast Threat Intelligence Team. \(2018, March 8\). New investigations into the CCleaner incident point to a possible third stage that had keylogger capacities. Retrieved March 15, 2018.](https://blog.avast.com/new-investigations-in-ccleaner-incident-point-to-a-possible-third-stage-that-had-keylogger-capacities)
2. [Windows Defender Research. \(2018, March 7\). Behavior monitoring combined with machine learning spoils a massive Dofoil coin mining campaign. Retrieved March 20, 2018.](https://cloudblogs.microsoft.com/microsoftsecure/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign/)
3. [Command Five Pty Ltd. \(2011, September\). SK Hack by an Advanced Persistent Threat. Retrieved April 6, 2018.](https://www.commandfive.com/papers/C5_APT_SKHack.pdf)
4. [O'Gorman, G., and McDonald, G.. \(2012, September 6\). The Elderwood Project. Retrieved February 15, 2018.](http://www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)
5. [Trendmicro. \(2018, November 29\). Hacker Infects Node.js Package to Steal from Bitcoin Wallets. Retrieved April 10, 2019.](https://www.trendmicro.com/vinfo/dk/security/news/cybercrime-and-digital-threats/hacker-infects-node-js-package-to-steal-from-bitcoin-wallets)
6. [Brumaghin, E. et al. \(2017, September 18\). CCleanup: A Vast Number of Machines at Risk. Retrieved March 9, 2018.](http://blog.talosintelligence.com/2017/09/avast-distributes-malware.html)
7. [Rosenberg, J. \(2017, September 20\). Evidence Aurora Operation Still Active: Supply Chain Attack Through CCleaner. Retrieved February 13, 2018.](http://www.intezer.com/evidence-aurora-operation-still-active-supply-chain-attack-through-ccleaner/)
8. [Chiu, A. \(2016, June 27\). New Ransomware Variant "Nyetya" Compromises Systems Worldwide. Retrieved March 26, 2019.](https://blog.talosintelligence.com/2017/06/worldwide-ransomware-variant.html)
9. [US-CERT. \(2017, July 1\). Alert \(TA17-181A\): Petya Ransomware. Retrieved March 15, 2019.](https://www.us-cert.gov/ncas/alerts/TA17-181A)
10. [Maynor, D., Nikolic, A., Olney, M., and Younan, Y. \(2017, July 5\). The MeDoc Connection. Retrieved March 26, 2019.](https://blog.talosintelligence.com/2017/07/the-medoc-connection.html)

