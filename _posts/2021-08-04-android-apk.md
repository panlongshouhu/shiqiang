---
layout: post
title: apk命令签名
categories: Android
description: 用命令给apk进行签名
keywords: android, apk
---

jarsigner -verbose -keystore  D:\mykey\my.jks -signedjar D:\mykey\signed.apk D:\mykey\aaa\myunsign.apk  abc

D:\mykey\my.jks  秘钥地址

D:\mykey\signed.apk  签名包输出位置

D:\mykey\aaa\myunsign.apk   要打包的位置

abc  别名
