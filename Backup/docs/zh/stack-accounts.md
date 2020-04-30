# 账号密码

使用Mattermost，可能会用到的几组账号密码如下：

## Mattermost

在初始化安装的时候由用户自行设置

## MySQL

* 管理员账号：*`root`*
* 管理员密码：存储在您的服务器指定文件中：*/credentials/password.txt*。建议通过云控制台直接连接服务器，进入命令终端，运行`cat /credentials/password.txt` 命令获取数据库密码：
   ![运行cat命令](https://libs.websoft9.com/Websoft9/DocsPicture/zh/common/catdbpassword-websoft9.png)

> 需要登录MySQL，请参考 [MySQL可视化管理](/zh/admin-mysql.md)

## Linux

* 主机地址：服务公网IP地址
* 连接方式：云控制台在线SSH 或 SFTP客户端工具 或 SSH客户端工具
* 管理员密码：创建服务器的时候自行设置，若不记得密码需要通过云控制台重置。
* 管理员账号：不同的云平台有一定的差异
   |  云平台   |  管理员账号   | 其他|
   | --- | --- | --- |
   |  Azure   |  创建服务器的时候自行设置   | [如何开启root账户？](https://support.websoft9.com/docs/azure/zh/server-login.html#示例2：启用系统root账号) |
   |  AWS Centos 系统   |  centos   | [如何开启root账户？](https://support.websoft9.com/docs/aws/zh/server-login.html#示例2：启用系统root账号) |
   |  AWS Ubuntu 系统  |  ubuntu   | [如何开启root账户？](https://support.websoft9.com/docs/aws/zh/server-login.html#示例2：启用系统root账号)  |
   |  阿里云，华为云，腾讯云   |  root   | |