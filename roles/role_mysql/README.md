Ansible Role: mysql
=========

本 Role 在CentOS或者Ubuntu服务器上安装和配置 mysql。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux|
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在语法上不依赖其他 role 的变量，但程序运行时需要确保已经运行：common。以 mysql 为例：

```
  roles:
   - {role: role_common, tags: "role_common"}   
   - {role: role_cloud, tags: "role_cloud"}
   - {role: role_mysql, tags: "role_mysql"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| mysql_version | [ 5.5, 5.6, 5.7, 8.0 ] | 字符串 |是|
| mysql_root_password | [ "123456"] | 字符串 |是|
| mysql_remote | [ "true", "false" ] | 字符串 |是|
| mysql_databases | []   | 字典 |否|
| mysql_users | []   | 字典 |否|

注意：
1. mysql_version, mysql_remote  的值在 mysql.yml 中由用户选择输入；
2. mysql_root_password，mysql_databases，mysql_users 的值在主变量文件[main.yml](https://github.com/Websoft9/ansible-mysql/blob/master/vars/main.yml)中定义。


## Example

```
- name: MariadDB
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
   - {role: role_common, tags: "role_common"}   
   - {role: role_cloud, tags: "role_cloud"}
   - {role: role_mysql, tags: "role_mysql"}
   - {role: role_docker, tags: "role_docker", when: phpmyadmin_install_docker}
   - {role: role_docker_phpmyadmin, tags: "role_docker_phpmyadmin", when: phpmyadmin_install_docker}
   - {role: role_init_password, tags: "role_init_password"}
   - {role: role_end, tags: "role_end"} 
```

## FAQ
