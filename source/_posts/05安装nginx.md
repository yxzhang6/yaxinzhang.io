---
title: linux nginx
tags:
  - nginx
abbrlink: d6d48d0f
---
> 怎么理解ngnix？
  反向代理，负载均衡。当网站的访问量达到一定程度后，单台服务器不能满足用户的请求时，需要用多台服务器集群可以使用nginx做反向代理。并且多台服务器可以平均分担负载，不会因为某台服务器负载高宕机而某台服务器闲置的情况。

##第一步
cd /developer/setup/
安装ngnix
sudo wget http://learning.happymmall.com/nginx/linux-nginx-1.10.2.tar.gz
安装全部的依赖
sudo yum -y install gcc zlib zlib-devel pcre-devel openssl openssl-devel
解压ngnix
sudo tar -zxvf linux-nginx-1.10.2.tar.gz
进入ngnix目录
cd /developer/setup/
cd nginx-1.10.2/

sudo ./configure
sudo make
sudo make install
pwd            查看当前位置 
whereis nginx  查看ngnix的配置在哪个目录路径
cd /usr/local/nginx/
cd conf     nginx配置目录
sudo vim nginx.conf    编辑： include vhost/*.conf;     保存

##第二步
cd /usr/local/nginx/conf
sudo mkdir vhost 
cd  vhost/
sudo wget    下载下面4个文件

sudo wget http://learning.happymmall.com/nginx/linux_conf/vhost/admin.happymmall.com.conf
sudo wget http://learning.happymmall.com/nginx/linux_conf/vhost/happymmall.com.conf
sudo wget http://learning.happymmall.com/nginx/linux_conf/vhost/img.happymmall.com.conf
sudo wget http://learning.happymmall.com/nginx/linux_conf/vhost/s.happymmall.com.conf
cd /usr/local/nginx
cd sbin/
sudo ./nginx    执行命令
cd /usr/local/nginx/conf
sudo vim nginx.conf  编辑文件
：set nu     显示行号
cd /usr/local/nginx/sbin/
sudo ./nginx


完成