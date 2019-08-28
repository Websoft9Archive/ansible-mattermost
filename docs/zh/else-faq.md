# FAQ

#### Mattermost 与 Slack 有什么区别？

参考官方文档 [Mattermost vs Slack](https://mattermost.com/mattermost-vs-slack/)

#### Mattermost提供客户端吗？

提供，[下载地址](https://mattermost.com/download/#mattermostApps)

#### Mattermost提供CLI工具吗？

提供，参考[官网CLI文档](https://docs.mattermost.com/administration/command-line-tools.html#using-the-cli)

#### Mattermost支持多语言吗？

支持多语言（包含中文），可以登录控制台，通过【SITE CONFIGURATION】>【Localization】设置语言 

#### 如果没有域名是否可以部署 Mattermost？

可以，访问`http://服务器公网IP` 即可

#### 数据库 root 用户对应的密码是多少？
密码存放在服务器相关文件中：`/credentials/password.txt`

#### 是否有可视化的数据库管理工具？

有，内置phpMyAdmin，访问地址：http://服务器公网IP:9090

#### 是否可以修改Mattermost的源码路径？

可以，通过修改 [Nginx 虚拟主机配置文件](/zh/stack-components.md)中相关参数


#### 如何修改上传的文件权限?

```shell
chown -R nginx.nginx /data/wwwroot
find /data/wwwroot -type d -exec chmod 750 {} \;
find /data/wwwroot -type f -exec chmod 640 {} \;
```

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。