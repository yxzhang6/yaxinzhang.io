---
abbrlink: '0'
---
---
title: 云服务器 安装jdk  
tags:
  - linux
  - jdk
  - 环境配置
---
> linux 服务器安装jdk >>>>>>>>>>>>>>>>>>>>

##  第一步：
cd /
sudo mkdir developer
cd developer/
sudo mkdir setup
cd setup
sudo wget http://learning.happymmall.com/jdk/jdk-7u80-linux-x64.rpm
sudo chmod 777 jdk-7u80-linux-x64.rpm      修改权限命令（所有文件及子目录的文件拥有者权限设置为读、写、可执行）  变为绿色的，权限修改成功
## 第二步安装命令：
sudo rpm -vih jdk-7u80-linux-x64.rpm  
jdk的安装目录   
cd /usr/java/jdk1.7.0_80/   
## 第三步编辑 ：
sudo vim /etc/profile
复制环境配置——编辑——保存
首先用D盘里面有保存的文件
http://learning.happymmall.com/env/

##  第四步：使配置生效
sudo source /etc/profile    
完成  java -version