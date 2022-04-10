---
title: 小米AX3600开启外网WOL唤醒
date: 2022-04-10 08:15
categories: 教程
---
主要适用于如下情况,关机时间长了无法外网唤醒,只有内网可以唤醒
问题主要出现在arp绑定丢失,小米路由器web后台没有arp绑定功能,只能ssh登陆后绑定arp
前提是需要root路由器,ssh登陆后执行如下操作
1.vi /etc/ethers
增加如下配置 ip mac地址
192.168.1.xxx xxx
2.编辑/etc/rc.local
增加ip neigh add xxxip lladdr xxxmac地址 nud permanent dev br-lan
操作完后关闭电脑,重启路由器,执行arp 查看是否存在arp映射,存在就是ok了
