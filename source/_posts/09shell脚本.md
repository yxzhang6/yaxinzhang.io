---
title: linux shell脚本
tags:
  - linux
  - shell
abbrlink: '494e9656'
---
> linux 自动化发布脚本  >>>>>>>>>>>>>>>>>>>>

cd /developer/ 
sudo mkdir git-repository  
cd git-repository/ 
sudo git clone +代码路径
cd /   
权限命令：
sudo chown -R zhang /developer/      文件给予zhang权限
sudo chmod u+w -R /developer/         写 权限
sudo chmod u+r -R /developer/          读 权限
sudo chmod u+x -R /developer/          执行 权限

cd /developer/git-repository/         项目路径
git clone +代码路径   输入yes

##编辑脚本目录路径   
cd /developer/        sudo vim deploy.sh


./deploy.sh    发布脚本命令


##查看tomcat下面的root
cd /developer/apache-tomcat-7.0.73/webapps
cat index.xml

21232f297a57a5a743894a0e4a801fc3

##脚本发布 后端
cd /developer/ 
./deploy.sh   