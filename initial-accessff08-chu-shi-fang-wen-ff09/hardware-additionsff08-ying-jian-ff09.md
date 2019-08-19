# 硬件

计算机附件、计算或者网络设备可以作为攻击矢量接入目标来获得代码执行。虽然APT组织用得很少，但是很多渗透测试者使用硬件来获得目标的初始访问权限。利用商业的或者开源的产品可以实现被动网络监听、中间人流量解密、按键注入、通过DMA读取内核内存、向已有的网络中添加新的无线热点等等。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Limit Access to Resource Over Network](https://attack.mitre.org/mitigations/M1035) | Establish network access control policies, such as using device certificates and the 802.1x standard. Restrict use of DHCP to registered devices to prevent unregistered devices from communicating with trusted systems.[\[6\]](https://en.wikipedia.org/wiki/IEEE_802.1X) |
| [Limit Hardware Installation](https://attack.mitre.org/mitigations/M1034) | Block unknown devices and accessories by endpoint security configuration and monitoring agent. |

## 检测

资产管理系统可以帮助发现不该存在的计算机或者网络设备。

终端检测软件可以检测到通过USB、雷电口或者其他外置接口插入的硬件。

## 参考

[Michael Ossmann. \(2011, February 17\). Throwing Star LAN Tap. Retrieved March 30, 2018.](https://ossmann.blogspot.com/2011/02/throwing-star-lan-tap.html)

[Nick Aleks. \(2015, November 7\). Weapons of a Pentester - Understanding the virtual & physical tools used by white/black hat hackers. Retrieved March 30, 2018.](http://www.bsidesto.ca/2015/slides/Weapons_of_a_Penetration_Tester.pptx)

[Hak5. \(2016, December 7\). Stealing Files with the USB Rubber Ducky – USB Exfiltration Explained. Retrieved March 30, 2018.](https://www.hak5.org/blog/main-blog/stealing-files-with-the-usb-rubber-ducky-usb-exfiltration-explained)

[Ulf Frisk. \(2016, August 5\). Direct Memory Attack the Kernel. Retrieved March 30, 2018.](https://www.youtube.com/watch?v=fXthwl6ShOg)

[Robert McMillan. \(2012, March 3\). The Pwn Plug is a little white box that can hack your network. Retrieved March 30, 2018.](https://arstechnica.com/information-technology/2012/03/the-pwn-plug-is-a-little-white-box-that-can-hack-your-network/)

[Wikipedia. \(2018, March 30\). IEEE 802.1X. Retrieved April 11, 2018.](https://en.wikipedia.org/wiki/IEEE_802.1X)



