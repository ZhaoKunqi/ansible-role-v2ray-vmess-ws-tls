# Vultr租赁VPS并使用Ansible Playbook部署V2Ray-WS-TLS代理服务器最佳实践教程

# Vultr账户

1. 如果你没有Vultr账户，先在my.vultr.com注册一个Vultr账号

2. 登陆你的Vutlr账户，使用你的银行卡或者支付宝来给你的Vultr账户添加余额(10美元即可)

# 从Vultr租赁一个VPS

1. 进入https://my.vultr.com/ 页面，在Products - Compute 界面下点击Deploy Server按钮，进入部署新云服务器的界面

2. 服务器类型选择：选择 Cloud Compute - Intel Regular Performance 最廉价的套餐，5美元/月

3. 地区选择：如果你想直连可以选择新加坡、日本、韩国等地区，如果你想通过CloudFlare中转可以选择美国，比如硅谷或者洛杉矶

4. 服务器操作系统选择：推荐选择Alma Linux 9或者Rocky Linux 9

5. 服务器配置套餐选择：选最便宜的

6. 自动备份选项： 关闭自动备份每月省一美元，因为是假设代理服务器所以不需要数据备份，玩崩了直接重新建一个即可

7. 创建新的云实例VPS： 点击右下角的 Deploy Now按钮

至此，你的VPS应该已经开始被创建了，只需要稍等数分钟即可使用SSH远程连接到你刚刚创建的VPS

# 域名解析

在等待服务器安装完成的时间内您应该登录您的域名服务商提供的DNS解析记录管理页面，为您的域名添加一条新的A记录

例如您的域名为 aloha.com ,那么您可以将例如 server123.aloha.com 解析到您刚才从Vultr创建的新IP地址上

注意：如果您使用的域名解析服务商为CloudFlare这类，请注意在部署时不要打开CloudFlare的CDN功能，在部署完毕后才可以打开。

# SSH登录与使用Ansible部署

在使用SSH登录到您刚租赁的VPS云服务器以后，请跟随如下操作

1. 安装需要用到的软件包

```
dnf install git ansible-core -y
```

2. 获取Ansible Playbook

```
git clone https://github.com/ZhaoKunqi/ansible-v2ray-vmess-ws-tls.git
```

3. 进入项目的目录

```
cd ansible-v2ray-vmess-ws-tls
```

4. 修改配置文件
```
vi config.yml
```

5. 编辑以下内容

```
# 已经解析到本机IP(VPS的IP地址)的域名
custom_domain_name: 这里写你的域名,例如 server123.aloha.com

# ACME验证用的邮箱，写自己的电子邮箱
acme_email: 'acme@aloha.com'

# 自定义Nginx路径，随便写一个即可
custom_path: 'alohahahahaha'

# VMess的UUID(或密码)，可以使用uuidgen命令生成，也可以使用https://www.uuidgenerator.net/生成
uuid: '0cb8db1f-c794-49c4-acdb-25e97ef7fff2'
```

保存退出以后，运行Ansible Playbook

```
ansible-playbook site.yml
```

如果Ansible正常运行完，那说明您的Nginx服务器和V2Ray服务器都部署好了，您可以尝试连接。
