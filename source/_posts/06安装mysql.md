---
title: linux mysql
tags:
  - linux
  - mysql
abbrlink: e7832b36
---
> linux 服务器安装MySql >>>>>>>>>>>>>>>>>>>>

cd  /usr/zhang
sudo rpm -qal grep mysql-server 检测系统 有没有安装mysql
sudo yum -y install mysql-server   安装mysql      complete
情况1：CentOS 7 会安装失败
首先输入以下命令

 wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm

 sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm

ls -1 /etc/yum.repos.d/mysql-community*

sudo yum install mysql-server

无法自启动：
sudo systemctl start mariadb.service
sudo systemctl enable mariadb.service
sudo mysql_secure_installation

sudo vim /etc/my.cnf   编辑下面文件的字符集       


sudo chkconfig mysqld on     配置mysql自启动 
sudo chkconfig --list mysqld   查看mysql自启动方式
sudo chkconfig --list mysqld 

sudo service mysqld restart    启动命令



mysql -u root 
select user,host,password from mysql.user;     查询
set password for root@localhost = password('root');   修改密码命令
在MySQL中，为了区分MySQL的关键字与普通字符，MySQL引入了一个反引号
set password for root@`instance-0nur4cgi`   = password('root');
set password for root@127.0.0.1 = password('root');


exit     退出
mysql -u root -p     带密码的密令
delete from mysql.user where user='';        删除匿名用户
flush privileges;        刷新

insert into mysql.user(user,host,password) values ("mmall","localhost",password("mmallpassword"));        新增访问用户的数据
select user,host,password from mysql.user;   查看访问用户列表
create database `mmall_learning` default character set utf8 COLLATE utf8_general_ci;    新建数据库
show databases;   查看数据库
赋予数据库一定权限
flush privileges;  刷新
grant all privileges on mmall_learning.* to mmall@localhost identified by 'mmallpassword'; 
flush privileges;  刷新

实用场景
exit 
cd  /developer
sudo wget http://learning.happymmall.com/mmall.sql
sudo mv mmall.sql mmall_learning.sql   进行重命令
mysql -u root -p 
show databases;       查看存在的数据库
use mmall_learning 
show tables;            查看数据库有没有表
source   /developer/mmall_learning.sql         运行mysql文件
select * from mmall_product\G; 查看表里面的数据

测试




删除数据库
drop database mmall_learning;