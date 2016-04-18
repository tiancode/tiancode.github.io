---
layout: post
title: 在Wifi网络中嗅探明文密码(HTTP POST请求)
---

全世界，现在大约50%的网站没有使用SSL加密，天朝尤其多。

我们都知道通过HTTP发送的数据都是明文，没有使用任何加密，即使是在数据敏感的登录页面。

本文的目的是：如果你在不熟悉的网络环境中，要注意提高警惕。

没有人希望自己的密码暴露给他人，so，不要嗅探（狗）他人的密码。

> 想象有一个攻击者坐在某个咖啡馆里，桌子上放着他的笔记本电脑并连着咖啡馆的免费wifi。这个家伙就可以非常容易的获得未加密的通信信息。

系统要求：

* Wireshark
* ARP欺骗攻击(ARP spoof attack)
* 无线网卡

*******

无线网卡监听模式和混杂模式有什么不同：

* 监听模式允许网卡不用连接wifi就可以抓取特性频道的数据，就是在空气中抓取某个波段的数据。可以用在[破解wifi密码](http://topspeedsnail.com/macbook-crack-wifi-with-wpa-wpa2/)上
* 混杂模式（连接wifi）就是接收所有经过网卡的数据包，包括不是发给本机的包，即不验证MAC地址
* 普通模式下网卡只接收发给本机的包

现在的无线路由器都是和主机直接通信，如果你直接使用嗅探工具，只会得到广播信息和自己的连接信息。为了得到网络中所有设备发送的的数据，攻击者必须想办法充当网关的角色，ARP欺骗攻击就干了这样一件事。如果有路由器控制权的话就省事了。

集线器可以直接嗅探，因为所有数据的发送形式是广播。看看这：集线器、交换机和路由器有什么不同。

ARP欺骗攻击(ARP spoof attack)：

* [使用Kali Linux执行中间人攻击](http://topspeedsnail.com/kali-linux-preform-man-in-middle-attack/)

* [Kali Linux ettercap的使用](http://topspeedsnail.com/kali-linux-ettercap-arp-spoof-attack/)

***

## 下载安装Wireshark

它也支持Windows、Mac OSX；下载地址：<https://www.wireshark.org/download.html>

Kali Linux自带了这个工具。

![Wireshark]({{ site.baseurl }}/images/2016/4/Screen Shot 2016-04-18 at 18.25.28.png)

还没写完









