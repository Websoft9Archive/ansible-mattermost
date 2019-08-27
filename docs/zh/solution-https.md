# SSL/HTTPS

Websoft9提供的部署包，默认已安装SSL模块支持和Let's Encrypt 免费的证书，并做了预设置。

如果你想使用免费证书，只需在服务中运行一条命令`certbot`就可以启动证书部署

如果你已经申请了证书，只需三个步骤，即可完成HTTPS配置

1. 将申请的证书上传到 */data/cert* 目录
2. 在虚拟主机配置文件：*/etc/nginx/sites-available/default* 中插入**HTTPS 配置段**
3. 重启服务

配置HTTPS的前置条件、HTTPS 配置段模板、注意事项、详细步骤以及故障诊断等具体方案，请参考由Websoft9提供的 [《HTTPS 专题指南》](https://support.websoft9.com/docs/faq/zh/tech-https.html)

> 除了虚拟主机配置文件之外，HTTPS设置无需修改任何Nginx文件，请勿随意改动