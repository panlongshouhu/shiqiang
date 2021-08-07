---
layout: post
title: Android Studio因为hosts变更无法debug调试问题
categories: AndroidStudio
description: Android Studio因为hosts变更无法debug调试问题
keywords: Android Studio, Android, hosts
---

因为个人下载了SwitchHosts的原因，不小心把系统的hosts文件中的值全部删除了，但是作者本人不知情。直到发现Android Studio无法进行debug调试了，一直提示Error running 'Android Debugger (-1)': Invalid argument : Argument invalid \[port\] 这个错误。个人尝试各种猜测端口被占用的问题进行修复，发现无法成功，后来发现一篇博主的文章有说的hosts问题，这才想起来自己的系统hosts确实有所变动，故添加(mac系统)

127.0.0.1 localhost

255.255.255.255 broadcasthost

::1            localhost

这恢复三行(原来的值)然后重新启动Android Studio就可以调试了。
