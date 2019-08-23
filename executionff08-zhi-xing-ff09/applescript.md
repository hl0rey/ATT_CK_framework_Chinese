# AppleScript

（参考资料 [https://catalogimages.wiley.com/images/db/pdf/9780470562291.excerpt.pdf）](https://catalogimages.wiley.com/images/db/pdf/9780470562291.excerpt.pdf）)

macOS和OS X系统的程序互相通过发送AppleEvent消息的方式进行进程间通信（IPC）。在远程或者本地的脚本里使用这些消息是很简单的。Osascript可以执行AppleScript或者其他符合任何符号开放脚本体系结构的脚本语言（有一些其他语言针对OSA的实现）。可以通过osalang程序查看当前系统上已经安装的OSA语言。可以单独发送消息，也可以在脚本中发送消息。这些事件可以打开窗口、模拟按键、并且可以和大部分已经打开的本地的或者远程的程序进行交互。

攻击者可以利用它与已经打开的SSH连接交互、移动到远程机器、甚至可以弹个假的对话框。这些事件虽然不能远程启动程序（他们可以在本地启动），但是可以与已经启动的远程程序交互。因为这是个脚本语言，他也可以被用来作出常见的行为，比如通过python反弹shell。可以通过osascript 脚本路径的方式或者osascript -e “script here”的方式来执行脚本。

## 缓解

## 例子

## 检测

## 参考





