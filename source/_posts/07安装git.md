---
title: linux git
tags:
  - linux
  - git
abbrlink: d4c3ca1a
---
> linux 服务器安装git >>>>>>>>>>>>>>>>>>>>

cd /developer/setup/   安装资源路径

sudo wget http://learning.happymmall.com/git/git-v2.8.0.tar.gz

安装git的各种依赖
sudo yum -y install zlib-devel openssl-devel cpio expat-devel gettext-devel curl-devel perl-ExtUtils-CBuilder perl-ExtUtils- MakeMaker  

sudo tar -zxvf git-v2.8.0.tar.gz   解压git的压缩包
cd git-2.8.0/   进入压缩包路径
sudo make prefix=/usr/local/git all 创建一个指定路径的文件夹
sudo make prefix=/usr/local/git install     指定文件夹安装
whereis git  查看路径
sudo vim /etc/profile  环境变量变量文件夹路径
/usr/local/git/bin:   bin路径

source /etc/profile   使环境变量配置生效
git version 或者查看git --version   查看版本命令 

git config --global user.name "yxzhang6"  配置全局的用户名
git config --global user.email "yxzhang6@163.com"  
git config --global core.autocrlf false   无视两种电脑系统 换行符的  
git config --global core.quotepath off    避免中文乱码
git config --global gui.encoding utf-8 
ssh-keygen -t rsa -C "yxzhang6@163.com"
ssh-add ~/.ssh/id_rsa   把专用密钥添加到 ssh-agent 的高速缓存中
Could not open a connection to your authentication agent.
eval `ssh-agent`       高速缓存
ssh-add ~/.ssh/id_rsa   再一次执行  
cat ~/.ssh/id_rsa.pub     查看公钥
