# Knowage自动化安装与部署

本项目是基于Ansible的[Knowage](https://www.knowage-suite.com)自动化安装脚本，实现在Ansible上一键安装Knowage。本项目是开源项目，支持MIT开源协议。如果您不熟悉Ansible的使用，您可以直接使用我们在公有云上提供的镜像。

## 操作系统

目前仅支持Ubuntu16.x以上部署此脚本

## 服务器配置要求

最低3G内存，20G系统盘空间，否则无法安装

## 版本

本项目Knowage采用的源码部署方式，为了保证每次安装为最新版本，需要在运行脚本之前Knowage源码下载地址。

修改方法：roles/knowage/defaults/main.yml的 knowage_url 字段

源码下载地址：https://www.knowage-suite.com/site/knowage-download/

## 安装指南

本Ansible脚本支持root用户、普通用户（+su权限提升）等两种账号模式，也支持密码和秘钥对登录方式。

其中普通用户登录需要增加变量：

~~~
//假设普通用户的username为
admin_username: websoft9
~~~

## 组件
Knowage,Nginx,JAVA,MYSQL,phpMyAdmin(Docker)

## 使用指南

后台账号：
   - demo_admin/demo_admin
   - demo_user/demo_user
   
配置文件：/data/wwwroot/Knowage-Server-CE/conf/server.xml

文档链接：[readme.txt](readme.txt)
