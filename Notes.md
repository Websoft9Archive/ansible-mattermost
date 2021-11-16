# Mattermost Notes

组件名称：Mattermost  
安装文档：https://docs.mattermost.com/install/install-rhel-7.html   
下载地址：https://docs.mattermost.com/upgrade/version-archive.html#mattermost-team-edition  

## 概要

Mattermost 是一款易于使用、经过简化且可扩展的团队通信和企业消息传送系统。Mattermost 应用程序实现了团队在一处完成所有通信，所有人都可以更轻松地在组内或私人聊天内一起讨论问题。

## 环境要求

* 程序语言：Go
* 应用服务器：自带
* 数据库:  MySQL或PostgreSQL
* 依赖组件：    TLS     
* 代理服务器:     nginx
* 其他：

## 安装说明

本项目通过下载Mattermost源码进行安装,完整的"Mattermost"安装由三个主要组件组成：代理服务器、数据库服务器和"Mattermost"服务器,其中数据库为MySQL或PostgreSQL,代理是nginx。

下面基于不同的安装平台，分别进行安装说明。

### CentOS

```shell
# 安装msql数据库服务

#创建mattermost用户"mmuser"并设置密码
mysql> create user 'mmuser'@'%' identified by '密码';

#创建mattermost数据库
mysql> create database mattermost;

#为用户授予访问权限
mysql> grant all privileges on mattermost.* to 'mmuser'@'%';


# 官网下载mattermost server
X.X.X表示要下载的版本号,在此以5.4.0为例:
wget https://releases.mattermost.com/5.4.0/mattermost-5.4.0-linux-amd64.tar.gz

#提取matter server文件
tar -xvzf mattermost-5.4.0-linux-amd64.tar.gz

#将提取的文件移动到目录
sudo mv mattermost /opt

#为文件创建存储目录(存储目录将包含用户发布到 Mattermost 的所有文件和图像)
sudo mkdir /opt/mattermost/data

#设置运行此服务的系统用户和组并赋权
sudo useradd --system --user-group mattermost
sudo chown -R mattermost:mattermost /opt/mattermost
sudo chmod -R g+w /opt/mattermost
   
#配置后验证安装
sudo /opt/mattermost/bin/mattermost
(出现"Server is listening on [::]:8065"表示安装成功)
```



## 路径

* 程序路径：      /opt/mattermost
* 日志路径：      /opt/mattermost/logs/mattermost.log
* 配置文件路径：/opt/mattermost/config/config.json
* 其他...

## 配置

安装完成后，需要依次完成如下配置

```shell
#在/opt/mattermost/config/config.json中找到Sqlsettings
       "SiteURL     "设置为      "https://mattermost.example.com"
   "DriverName  "设置为  "mysql"
    "DataSource"   设置为  "mmuser:*mmuser-password*@tcp(*host-name-or-IP*:3306)/mattermost?charset=utf8mb4,utf8&readTimeout=30s&writeTimeout=30s"(数据库密码和主机ip根据实际填写)
```

## 账号密码

### 数据库密码

如果有数据库

* 数据库安装方式：自行安装
* 账号密码：自定义

### 后台账号

如果有后台账号

* 登录地址  http://ip:8065
* 账号密码  
* 密码修改方案：最好是有命令行修改密码的方案


## 服务

本项目安装后无 服务

## 环境变量

列出需要增加的环境变量以及增加环境变量的命令：

* 名称 | 路径

## 版本号

通过如下的命令获取主要组件的版本号: 

```
# Check Mattermost version

```

## 常见问题

#### 有没有管理控制台？

*http:// 公网 IP:8065* 即可访问控制台

#### 本项目需要开启哪些端口？

| item      | port  |
| --------- | ----- |
|mattermost  |  8065  |

#### 有没有CLI工具？

无

## 日志

* 2020-04-21 完成CentOS安装研究
