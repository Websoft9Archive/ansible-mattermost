# Mattermost自动化安装与部署

## 操作系统

目前仅支持Ubuntu16.x以上

## 版本

由于Mattermost是通过下载源码安装，而源码下载的URL地址中是根据版本号来命名文件名称，因此设计一个`mattermost_ver`变量作为版本号来控制下载地址。此变量存在 `/roles/mattermost/main.yml`文件中。

## 安装指南

支持root用户、普通用户（+su权限提升）等两种账号模式，也支持密码和秘钥对登录方式。

## 使用指南

[中文](https://support.websoft9/docs/mattermost/zh) | [英文](https://support.websoft9/docs/mattermost)