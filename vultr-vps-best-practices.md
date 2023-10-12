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
