---
title: linux 安装tomcat
tags:
  - linux
  - tomcat
abbrlink: 4584b520
---
> linux 服务器安装tomcat >>>>>>>>>>>>>>>>>>>>

## 第一步下载：
cd /developer/
sudo wget http://learning.happymmall.com/tomcat/apache-tomcat-7.0.73.tar.gz
## 第二步安装：
sudo tar -zxvf apache-tomcat-7.0.73.tar.gz       解压

sudo mv apache-tomcat-7.0.73.tar.gz  setup/     移动安装文件
## 第三步：配置UTF-8
进入  cd apache-tomcat-7.0.73/
编辑： sudo vim conf/server.xml
/8080   搜索
：noh  去除高亮
修改 Tomcat的字符集修改好      URIEncoding="UTF-8"
##第四步：运行    
cd /developer/apache-tomcat-7.0.73/bin          运行tomcat 
 (安全组策略和防火墙都是空的时候，在外网可以访问到
cd bin
sudo ./startup.sh
