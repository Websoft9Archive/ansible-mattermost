Ansible Role: common
=========

本 Role 用于在CentOS或者Ubuntu服务器上安装常见工具和配置系统自动更新

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux|
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  Linux |


## Related roles

本 Role 在其他 roles 之前运行。


## Variables

暂无


## Example

```
- name: LAMP
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
    - { role: role_common }
```

## FAQ


