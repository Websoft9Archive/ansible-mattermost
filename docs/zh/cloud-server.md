# 服务器入门

通过云服务器部署和使用开源软件，需要掌握一些基本的云服务器相关操作，例如：

- 连接云服务器、管理文件
- 修改安全组
- 云服务器自动备份
- 增加数据盘

以上操作，不同的云平台有一定的差异。因此，请阅读[《云服务器快速入门》](https://support.websoft9.com/docs/cloud/zh) 中对应的云平台内容。

对于连接云服务器来说，操作基本相同，下面详细说明：

## 使用命令行连接服务器

命令行（Command）是Linux系统最基本的操作，为了简化命令行登录，主流的云厂商控制台都提供了网页版的在线SSH登录工具。

找到服务器实例，点击 **命令行连接** 即可。

> 如果您不习惯使用云平台的提供的在线SSH命令行工具，您可以下载SSH客户端工具（例如：[putty](https://putty.org/)），配置登录信息之后开始使用。

命令行连接服务器之后，如下两个最常用的操作范例是需要掌握的：

### 获取数据库密码

为了安全考虑，用户每一次部署，都会生成唯一的随机数据库密码，存放在服务中。只需如下的一条命令，即可查看

``` shell
cat /credentials/password.txt

//运行结果
MySQL username:root
MySQL Password:@qDg1Vq1!V
```

### 启用系统root账号

部分云厂商出于安全和法规要求，默认情况下没有开放Linux的root账号，只给用户提供了普通账号。如果您希望使用root账号，通过下面的步骤启用之：

``` shell
sudo su
sudo sed -i 's/#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config
sudo systemctl restart sshd
sudo passwd root
```



## 使用SFTP连接服务器

SFTP是使用SSH协议的FTP模式，也称之为安全增强型的FTP。SFTP工具是Linux用户最喜欢的一种操作方式，下面以WinSCP这款SFTP工具为例，详细说明SFTP的使用。

### 配置WinSCP

1. 下载[WinSCP](https://winscp.net/) ，安装后，启动WinSCP并新建一个连接
3. 根据云服务器的 **密码验证和秘钥对** 两种验证方式分别说明：

   * 密码验证方式设置（最常见的方式）
   ![密码验证方式](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/winscp-newsite.png)

   * 秘钥对验证方式设置
   ![秘钥对验证方式](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/winscp-secrets-websoft9.png)
4. 验证方式设置好之后，点击"登录"
5. 登录之后，系统提示您是否保存登录信息，选择"是"
6. 成功连接后的界面
  ![WinSCP管理界面](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/websoft9-winscp-success.png)

### 管理文件

WinSCP通过拖拽，就可以方便上传下载文件，并可以在线修改文件

1. 一般来说网站的文件都放在/data/wwwroot/目录下
2. 右键单击服务器上一个文件或文件夹，可以对云服务器进行多种操作
  ![管理文件](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/websoft9-winscp-youjian.png)
3.以修改文件权限为例的相关界面如下
  ![管理文件](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/websoft9-winscp-quanxian.png)

### 运行命令

WinSCP是自带命令运行功能的，虽然命令功能仅限于运行非交互式命名（即命令执行过程中无需反馈和过程中的输入），但对于初学者确简单实用。

1. WinSCP登录到服务器，点击菜单来的命令窗口图标（快捷键Ctrl+T也可以）
![命令行工具](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/winscp-ucmd-websoft9.png)
2. 在弹出的命令运行窗口执行命令（每次一条命令），以查询内存使用为例，运行命令 `free -m`
![命令行工具](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/wincp-showmemory-websoft9.png)


### 集成Putty

在某些特定的常见下，可能需要使用Putty来运行命令。由于Putty是一个命令操作界面，每次使用的时候都需要输入root密码，如果密码比较复杂，会让人感觉比较麻烦。其实WinSCP是可以集成Putty的，集成后，通过Winscp就可以打开Putty，自动登录到服务器。

1. 打开Winscp-选项-集成-应用程序。Putty/terminal客户端路径这里为你本地putty.exe程序的路径
![命令行工具](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/websoft9-winscp-putty.png)

2. 集成成功后，只需要通过Winscp的窗口快捷方式即可打开Putty
![命令行工具](http://libs.websoft9.com/Websoft9/DocsPicture/zh/winscp/websoft9-winscp-puttyopen.png)

> 通过Winscp打开Putty操作与直接打开putty没有区别

## 安全组设置

不同云平台的安全组设置有一定的差异，因此我们提供了多个云平台相关文档供您参考：

[Azure设置](http://www.websoft9.com)  | [AWS设置](http://www.websoft9.com) | [阿里云设置](http://www.websoft9.com)  |  [华为云设置](http://www.websoft9.com) | [腾讯云设置](http://www.websoft9.com)