# Ansible-V2Ray-VMess-WebSocket-TLS-Web

本项目是一个Ansible Playbook，这个Playbook可以被用来在服务器上自动化部署V2Ray代理服务器。

本项目中的Playbook会在服务器上安装V2Ray、Nginx和acme.sh以及其依赖关系包，并且部署一个VMess协议，使用WebSocket和TLS的代理服务器，也可以套CDN使用。

## 兼容环境操作系统

* RHEL 8/9

* CentOS Stream 8/9
 
* Alma Linux 8/9

* Rocky Linux 8/9

# 最佳实践

## 安装Ansible)

RHEL及其下游8版本的系统: `dnf install ansible -y`

RHEL及其下游9版本的系统: `dnf install ansible-core -y`

## Linode月抛小鸡部署最佳实践

使用便宜Linode月抛小鸡

未完待续 忙完了再写
