# 参数

Mattermost 部署包预制支持 Mattermost 运行所需一序列支持软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### Mattermost

Mattermost 安装目录： */opt/mattermost/*  
Mattermost 配置文件： */opt/mattermost/config/config.json*

> Metabase 配置文件中包含数据库连接信息，更改了 MySQL 数据库账号密码，此处也需要对应修改

### Go

Mattermost 使用 Go 语言开发，镜像默认支持 Go 程序部署

### Nginx

Nginx 虚拟主机配置文件：*/etc/nginx/sites-available/default*  
Nginx 主配置文件： */etc/nginx/nginx.conf*  
Nginx 日志文件： */var/log/nginx/*

### MYSQL

MySQL 安装路径: */usr/local/mysql* 
MySQL 数据文件 */data/mysql*  
MySQL 配置文件: */etc/my.cnf*  
MySQL 可视化管理地址: *http://服务器公网IP:9090*

MySQL 用户名和密码请参考 [账号密码](/zh/stack-accounts.md) 章节。


## 端口号

下面是您在使用本镜像过程中，需要用到的端口号，请通过云控制台安全组进行设置

| 名称 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| MySQL | 3306 | 远程连接MySQL | 可选 |
| HTTP | 80 | 通过http访问Metabase | 必须 |
| HTTPS | 443 | 通过https访问Metabase | 可选 |
| phpMyAdmin on Docker | 9090 | 可视化管理MySQL | 可选 |

## 版本号

组件对应的基本版本号可以通过云市场商品页面查看，但部署到您的服务器之后，版本会有一定的升级，故更为精准的版本请通过在服务器上运行命令查看：

```shell
Nginx version:
nginx -v

MySQL version:
mysql -V

Dokcer:
docker --version
```