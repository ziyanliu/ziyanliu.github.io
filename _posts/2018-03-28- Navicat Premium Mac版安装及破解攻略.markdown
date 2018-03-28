---
layout: post
title:  "Navicat Premium Mac版安装及破解攻略"
tags:  "iOS"
date:   2018-03-28 14:19:56 +0800
categories: 总结
---

### Navicat Premium是什么？

> Navicat Premium 是一套多连接数据库开发工具，让你在单一应用程序中同时连接多达六种数据库：MySQL、MariaDB、SQL Server、SQLite、Oracle 和 PostgreSQL，可一次快速方便地访问所有数据库。

## 安装

* 一、下载Navicat Premium

1.进入官网[http://www.navicat.com.cn/products](http://www.navicat.com.cn/products) 点击免费使用

2.找到macOS Navicat Premium 版本 12 这里有三个位置，如果点击的下载速度较慢 可以使用另一个位置试试 或许速度上有惊喜


* 二、下载DoubleLabyrinth/navicat-keygen

地址[https://github.com/DoubleLabyrinth/navicat-keygen](https://github.com/DoubleLabyrinth/navicat-keygen)

注意切换到Mac版分支

* 破解

1.打开终端 进入navicat-keygen 命令如下：

```bash
$ cd navicat-keygen

$ make release
```

2.终端输入命令


```bash
$ openssl genrsa -out 2048key.pem 2048

$ openssl rsa -in 2048key.pem -pubout -out rpk

```

完成之后在navicat-keygen所在的文件夹中会出现 2048key.pem 和 rpk  如下图：


<img src="/images/posts/navicat/navicat" height="160" width="600">

3.用上一步得到的rpk替换Navicat Premium.app/Contents/Resources/rpk

4.终端输入$ ./navicat-keygen 2048key.pem 然后会让输入姓名 组织 自己随意填写就行 然后会得到激活码

5.断开网络  打开Navicat Premium  点击注册 输入激活码。提示出错 点击手动激活 得到请求码

6.复制请求码放入终端 回车两次 得到激活码

7.复制终端得到的激活码 放到手动激活界面的下部窗口 点击激活 完成


