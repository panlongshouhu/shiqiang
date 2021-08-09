---
layout: post
title: macOS 10.15 Catalina app损坏问题
categories: Mac
description: macOS 10.15 Catalina xxx.app已损坏，无法打开，你应该将它移到废纸篓解决方法
keywords: mac, Catalina
---

更新macOS 10.15 Catalina后，很多在10.14上可以使用的App都会提示提示【xxx已损坏，无法打开，你应该将它移到废纸篓解决办法】，哪怕你在【安全与隐私 》 通用】中已经开启了“任何来源”，但还是会这样提示，下边下面就教大家如何修复。

最新解决方案

[查看最新解决方法](https://www.macwk.com/article/macos-file-damage)

准备

先打开 系统偏好设置 -> 安全与隐私 -> 通用 选项卡，检查是否已经启用了 任何来源 选项。如果没有启用，先点击左下角的小黄锁图标解锁，然后选中任何来源。

如果没有这个选项，我们打开终端，输入以下命令 (可以通过点击屏幕右上角的搜索图标，输入终端快速运行)：

sudo spctl --master-disable

然后按下键盘的回车键（return），输入密码，再按回车键，完成。

输入命令回车后会看见个 password 后面还有个钥匙图标，在钥匙图标后面输入你自己电脑解锁密码（输入的时候不显示你输入的密码，感觉就是输入不了东西一样，也不用管，凭感觉输入完正确解锁密码后按回车键）

好了，现在回到 系统偏好设置 -> 安全性与隐私 -> 通用 里，就会发现已选中任何来源选项了。

一般执行完命令会默认选中的，如果没有选中，解锁一下选中就可以了！

到这里一般情况下应用都可以运行了，特别是 macOS 10.14 及以下系统

但是 macOS 10.15x 系统对于未签名的应用又进一步收缩了权限，众所周知破解软件基本上不会进行签名的，特别是所以当我们在 10.15.x 系统上运行破解软件的时候可能还会提示xxx.app已损坏，不过没关系，我们通过命令绕过苹果的公证 Gatekeeper 就可以了。

绕过公证：

打开终端，输入以下命令：

sudo xattr -rd com.apple.quarantine /Applications/xxxxxx.app

将上面的 xxxxxx.app 换成你的App名称，比如 Sketch.app

sudo xattr -rd com.apple.quarantine /Applications/Sketch.app

或者复制以下命令粘贴到终端后

sudo xattr -rd com.apple.quarantine

打开Finder（访达），点击左侧的 应用程序，将应用拖进终端中，然后按键盘的回车键（return），输入密码，再按回车键，完成。

注意 quarantine 后面必须有个空格

<img src="/images/posts/mac_catalina.webp" width="80%" alt="拖拽演示图" />

好了再看一下是不是可以打开APP了！

最后

如果您嫌麻烦，您也可以下载 macwk.com 编写的 macOS工具箱，可以快速执行命令操作：

下载完成后，打开dmg文件，按住键盘上的control键，然后单击或者右键点击macOS小助手应用图标，再点击打开即可！

输入序号：14，然后将应用拖进窗口中，按下回车，输入密码即可！