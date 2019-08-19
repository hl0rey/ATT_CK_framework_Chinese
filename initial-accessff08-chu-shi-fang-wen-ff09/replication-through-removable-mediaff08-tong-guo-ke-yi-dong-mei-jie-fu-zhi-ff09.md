# 通过可移动媒介复制

攻击者可能直接走到系统内部，目标可能是断网机或者物理隔离的机器，通过可移动媒介将恶意软件复制到目标机器上（利用当媒介插入电脑即自动运行某程序的功能）。如果是为了横向移动，攻击者可能会更改可移动媒介中的文件或者拷贝恶意文件进去，将其重命名为一个合法的文件的命名，来欺骗用户在一个独立的机器上运行。如果是为了初始访问，攻击者可能会手工操作可以的媒介，修改格式化该媒介的系统、或者修改该媒介的固件。

## 缓解

| Mitigation | Description |
| :--- | :--- |
| [Disable or Remove Feature or Program](https://attack.mitre.org/mitigations/M1042) | Disable Autorun if it is unnecessary. Disallow or restrict removable media at an organizational policy level if it is not required for business operations.[\[14\]](https://support.microsoft.com/en-us/kb/967715)[\[15\]](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx) |
| [Limit Hardware Installation](https://attack.mitre.org/mitigations/M1034) | Limit the use of USB devices and removable media within a network. |

## 例子





