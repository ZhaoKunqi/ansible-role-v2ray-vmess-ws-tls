# Ansible-V2Ray-VMess-WebSocket-TLS-Web

本项目是一个Ansible Playbook，这个Playbook可以被用来在服务器上自动化部署V2Ray代理服务器。

本项目中的Playbook会在服务器上安装V2Ray、Nginx和acme.sh以及其依赖关系包，并且部署一个VMess协议，使用WebSocket和TLS的代理服务器，也可以套CDN使用。

## 兼容环境操作系统

* RHEL 8/9

* CentOS Stream 8/9
 
* Alma Linux 8/9

* Rocky Linux 8/9

# 更新日志

## 2023年10月11日: 

有一些VPS厂商会默认删除VPS镜像中的防火墙并且设置SELinux为不激活的状态来减少用户可能遇到的麻烦，

在这种被二次定制过的系统中运行时会找不到firewalld服务，也无法改成permissive模式，于是对site.yml进行更新，使其支持在这种环境下部署。

1. 修复了在已经将firewalld.service删除掉的VPS上运行时报错的问题
 
2. 修复了在已经将SELinux设置为disabled模式的VPS上运行时报错的问题

# 最佳实践

[Linode小鸡VPS最佳实践部署教程 linode-vps-best-practices.md](linode-vps-best-practices.md)

[Vultr小鸡VPS最佳实践部署教程 vultr-vps-best-practices.md](vultr-vps-best-practices.md)

[AWS EC2小鸡VPS最佳实践部署教程 aws-ec2-vps-best-practices.md](aws-ec2-vps-best-practices.md)

[AWS Lightsail小鸡VPS最佳实践部署教程 aws-lightsail-best-practices.md](aws-lightsail-vps-best-practices.md)

[GCP谷歌云计算引擎VPS小鸡最佳实践部署教程 gcp-gce-best-practices.md](gcp-gce-vps-best-practices.md)

未完待续 忙完了再写
