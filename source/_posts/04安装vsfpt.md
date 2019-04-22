---
abbrlink: '0'
---
title: linux vsfpt
tags:
  - linux
  - vsfpt
---
> linux 服务器安装vsfpt >>>>>>>>>>>>>>>>>>>>

 ## 第一步直接安装
 cd developer/
 sudo yum -y install vsftpd
 
 创建一个vsfpt  user 是用来操作vsftpd的权限，没有登录云服务器的权限，
 ##第二步
 cd /
 sudo mkdir product
 cd /product/
 sudo mkdir ftpfile（可以省略）
 创建一个vsfpt  user 
 sudo useradd ftpuser -d /product/ftpfile -s /sbin/nologin
 赋予ftpfile权限
 sudo chown -R ftpuser.ftpuser ./ftpfile
 sudo passwd ftpuser     重置密码   
 ##第三步
 cd /etc/vsftpd/
 sudo vim chroot_list  
 添加ftpuser
 ##第四步 
 修改安全策略共有两种方式
 sudo vim /etc/selinux/config  
 
  sudo setsebool -p ftp_home_dir 1 命令直接修改
 ##第五步 vsftpd.conf配置文件
 重命名命令：
 sudo mv vsftpd.conf vsftpd.conf.bak  复制备份（重新命名的意思）
 sudo wget http://learning.happymmall.com/vsftpdconfig/vsftpd.conf
 ##第六步：
 sudo service vsftpd start