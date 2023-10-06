# Ansible-V2Ray-VMess-WebSocket-TLS-Web

本项目是一个Ansible Playbook，这个Playbook可以被用来在服务器上自动化部署V2Ray代理服务器。

本项目中的Playbook会在服务器上安装V2Ray、Nginx和acme.sh以及其依赖关系包，并且部署一个VMess协议，使用WebSocket和TLS的代理服务器，也可以套CDN使用。

## 兼容环境操作系统

* RHEL 8/9

* CentOS Stream 8/9
 
* Alma Linux 8/9

* Rocky Linux 8/9

# 最佳实践

## 安装Ansible

RHEL及其下游8版本的系统: `dnf install ansible -y`

RHEL及其下游9版本的系统: `dnf install ansible-core -y`

## Linode月抛小鸡部署最佳实践

买一个Linode的便宜VPS(或者月抛小鸡)

配置要求: 可以选最便宜的配置, 有IPv4就可以

操作系统: CentOS Stream 9(推荐)

安装需要用到的软件包

```
dnf install git ansible-core -y
```

获取Ansible Playbook

```
git clone https://github.com/ZhaoKunqi/ansible-v2ray-vmess-ws-tls.git
```

进入项目的目录

```
cd ansible-v2ray-vmess-ws-tls
```

修改配置文件
```
vi config.yml
```

编辑以下内容

```
# 已经解析到本机IP(VPS的IP地址)的域名, 如果是CloudFlare之类的话需要先关闭CDN.
custom_domain_name: 这里写你的域名,例如 server01.example.com

# ACME验证用的邮箱，写自己的电子邮箱
acme_email: 'raman@rebecca.net'

# 自定义Nginx路径，随便写一个即可
custom_path: 'b5c403e4'

# VMess的UUID(或密码)，可以使用uuidgen命令生成，也可以使用https://www.uuidgenerator.net/生成
uuid: 'f7fd888b-03ac-43d4-a650-3b2c098da1f3'
```

保存退出以后，运行Ansible Playbook

```
ansible-playbook site.yml
```

在Playbook运行完之后，如果没有报错，即表示部署成功。

部署成功后，可以在CloudFlare将CDN记录改成CloudFlare CDN转发。


未完待续 忙完了再写
