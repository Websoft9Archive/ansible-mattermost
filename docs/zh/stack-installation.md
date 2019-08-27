# 初始化安装

在云服务器上部署了 Metabase 镜像之后，请参考下面的步骤来使用它。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 如果您打算通过域名访问Metabase软件，请通过域名控制台完全一个域名解析（非必须）

## Metabase 安装向导

1. 使用本地电脑的 Chrome 或 Firefox 浏览器访问网址：http://domain name 或 http://Internet IP, 就进入了软件的引导首页
![Metabase初始化页面](https://libs.websoft9.com/Websoft9/DocsPicture/en/metabase/metabase-start-websoft9.png)

2. 软件的加载速度比较慢，耐心等待1-3分钟，直至出现如下的界面。
![开始安装Metabase](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-starty-websoft9.png)

3. 点击“让我们开始吧”，接下来首先设置登录账号，完成后进入下一步
4. 添加你的数据：可以选择使用的数据类型来连接一个需要分析的外部数据库，如果没有也可以点击“我之后再添加”，这样系统会默认给 Metabase 增加一个H2演示数据
![配置Metabase](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-installdb-websoft9.png)

5. 安装成功后的界面，点击“带我去Metabase”登录后台
![Metabase安装成功](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-installss-websoft9.png)

6. 以H2演示数据为例，开始数据分析工作
![Metabase后台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-dashborad-websoft9.png)

7. Metabase有强大的系统管理能力：后台->设置->管理员，进入系统管理界面
![Metabase后台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-admin-websoft9.png)

8. 通过“添加一个数据库”来增加一个数据分析源
![Metabase后台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-adddb-websoft9.png)

9. 通过点击“人员管理”标签，管理使用Metabase用户，包括增加用户、修改密码等
![Metabase后台](https://libs.websoft9.com/Websoft9/DocsPicture/zh/metabase/metabase-users-websoft9.png)

10. 需要了解更多Metabase的使用，请参考官方文档：[Metabase Documentation](https://metabase.com/docs/latest/)

## 常见问题

#### 浏览器打开IP地址，无法访问Metabase（白屏没有结果）？

您的服务器对应的安全组80端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 本部署包采用的哪个数据库来存储 Metabase 数据？

是MySQL，不是默认的H2，H2只能用于测试环境
