Ansible Role: Docker
=========

本 Role 用于在PHP运行环境下安装 [Docker](https://www.docker.com/)。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 |
| Python 版本 | Python2  |
| Python 组件 |  requests, docker-compose  |
| Runtime |  |

注意： requests 需要更新为最新版本，否则 Docker API 无法使用(ansible docker 是通过 Docker API 管理 Docker)。


## Related roles

本 Role 在语法不依赖其他 role 的变量，但程序运行时需要确保已经运行： common。例子如下：

```
  roles:
    - { role: role_common }
    - { role：role_docker }
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| docker_images | 容器镜像名称 | 字符串 | 否 |

注意： 
1. docker_images：该变量只在安装的同时需要拉取容器镜像时赋值。

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
   - {role: role_docker, tags: "role_docker"}

## FAQ
