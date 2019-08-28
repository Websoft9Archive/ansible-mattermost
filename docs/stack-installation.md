# 初始化安装

在云服务器上部署 Mattermost 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:80** 端口是否开启
3. 若想用域名访问 Mattermost，请先到 **域名控制台** 完成一个域名解析

## Mattermost 安装向导

1. 本地电脑的 Chrome 或 Firefox 浏览器访问网址：`http://域名` 或 `http://服务器公网IP`, 进入引导页面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-install-websoft9.png)
2. 设置后台管理员账号和密码，开始创建账号
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-createdaccount-websoft9.png)
3. 开始创建团队 或 登录到系统控制台
5. 打开：【SITE CONFIGURATION】>【Localization】设置你所需的语言
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-language-websoft9.png)
5. 退出并重新登录，所选语言生效

> 需要了解更多 Mattermost 的使用，请参考官方文档：[Matterbase Administrator’s Guide](https://docs.mattermost.com/guides/administrator.html)

## 常见问题

#### 浏览器打开IP地址，无法访问 Mattermost（白屏没有结果）？

您的服务器对应的安全组80端口没有开启（入规则），导致浏览器无法访问到服务器的任何内容

#### 本部署包采用的哪个数据库来存储 Mattermost 数据？

是MySQL
