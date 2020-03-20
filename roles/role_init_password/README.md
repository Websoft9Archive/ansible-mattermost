Ansible Role: init_password
=========

本 Role 用于在在 CentOS, Ubuntu 和 AmazonLinux 服务器上初始化随机密码

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu AmazonLinux |
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime | MySQL, MariaDB, PostgreSQL, MongoDB |


## Related roles

本 Role 在语法上引用了主变量，程序运行时需要确保已经运行： mysql | mariadb | postgresql | mongodb 等 Role。以 mysql 为例：

```
  roles:
   - {role: role_common, tags: "role_common"}   
   - {role: role_cloud, tags: "role_cloud"}
   - {role: role_mysql, tags: "role_mysql"}
   - {role: role_docker, tags: "role_docker"}
   - {role: role_docker_phpmyadmin, tags: "role_docker_phpmyadmin"}
   - {role: role_init_password, tags: "role_init_password"} 
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| init_db | mysql/mariadb/postgresql/moongodb[ user: username,  password: password ]   | 字典 | 否 |
| init_application | [...]   | 字典 | 否 |

注意：
1. init_application 和 init_application 初始化在项目主变量文件中统一修改。



## Example

```
- name: MySQL
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
   - {role: role_common, tags: "role_common"}   
   - {role: role_cloud, tags: "role_cloud"}
   - {role: role_mysql, tags: "role_mysql"}
   - {role: role_docker, tags: "role_docker"}
   - {role: role_docker_phpmyadmin, tags: "role_docker_phpmyadmin"}
   - {role: role_init_password, tags: "role_init_password"}
   - {role: role_end, tags: "role_end"} 
```

## FAQ


