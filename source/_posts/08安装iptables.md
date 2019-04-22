---
title: linux iptables
tags:
  - linux
  - iptables
  - JavaScript
abbrlink: c1c57924
---
> linux 服务器安装iptable >>>>>>>>>>>>>>>>>>>>

cd /etc/sysconfig/       防火墙的目录
ll | grep ipt   （查看是否有文件）模糊查询 文件    grep：检索目标行命令

##初始化iptables
sudo iptables -P OUTPUT ACCEPT
sudo service iptables save

sudo mv iptables iptables.bak 备份一下
sudo wget http://learning.happymmall.com/env/iptables   下载线上的iptables

sudo vim iptables   编辑文件

##重新启动防火墙
sudo service iptables restart 