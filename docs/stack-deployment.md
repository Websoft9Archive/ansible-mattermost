# Deployment

**Deployment is to copy the Mattermost pre-packaged online to your Cloud Server**. For example, after the user subscribe Mattermost on the Cloud Platform, the Platform will automatically copy the Mattermost to the corresponding Cloud Server.

- If Mattermost has been deployed, go to [Initial Installation](/zh/stack-installation.md) to complete the operation.
- If Mattermost is not deployed, you need to deploy Mattermost to your cloud server first.

We offer two deployment Mattermost scenarios (the deployment results are the same):

## Deploy by Image

**镜像**是指云服务器可选择的运行环境模板，一般包括操作系统和预装的软件。**镜像部署**就是用户基于镜像来创建云服务器，从而获得与镜像一致的系统环境。

对有云服务器使用经验的用户来说，镜像部署可以等同于“一键部署”。

我们在主流的云平台上发布了 [Mattermost 镜像](https://apps.websoft9.com/mattermost)供用户使用。云平台一般支持三种镜像部署方式：

* 在 **选购新服务器** 的时候，找到并选取 Mattermost 镜像作为服务器启动环境
* 在 **云市场（Marketplace）**  的 Mattermost 商品页面直接购买镜像
* 对于已有服务器，通过 **更换镜像（重装系统）** 的操作，将已有镜像替换为 Mattermost 镜像。

## Deploy by Script

**Script deployment** means running a script on the cloud server to pull the pre-packages online to your instance and configure it at the same time.

Websoft9 provide the opensource [Mattermost ansbile automation script](https://github.com/Websoft9/ansible-mattermost) on Github. If you are familiar with Ansible, you can deploy the Mattermost to the instance automaticly.

## Comparison

Although the results of the deploy by Image are consistent with the results of deploy by Script, what is the difference between the two deployment methods?

Suggest you read the document [Deploy by Image vs Deploy by Script](https://support.websoft9.com/docs/faq/bz-product.html#deployment-comparison)