# debianclash
参照油管UP主(米月大佬)灯脚脚本、yuanlam以及A-wing blog修改的一键安装Clash客户端 For Debian10。自用。。。不喜勿用

#支持Debian 10（其他系统未测试）

#脚本使用注意事项：脚本需在root用户下执行, 两种模式(redir-host / fake-ip)随意选择。

*Type1: Clash使用redir-host的DNS模式
```
apt install wget -y
```

```
bash <(wget --no-check-certificate -qO- https://raw.githubusercontent.com/poplovetorock/debianclash/master/1key)
```

*Type2: Clash使用fake-ip的DNS模式(安装完成后记得把DNS改为198.18.0.1)
```
apt install wget -y
```

```
bash <(wget --no-check-certificate -qO- https://raw.githubusercontent.com/poplovetorock/debianclash/master/1key_fakeip)
```
Clash管理
```
http://你的ip:9090/ui/                   #web界面

/home/clash/.config/clash/config.yaml    #配置文件地址
```

Smartdns命令

```
systemctl restart smartdns          #重新启动服务

systemctl status smartdns           #查看状态
```
unbound命令
```
systemctl restart unbound           #重新启动服务

systemctl status unbound            #查看状态
```
nftables命令
```
nft flush ruleset                   #清空设置

nft -f /etc/nftables.conf           #使新的设置生效

nft list ruleset                    #查看当前 nftables 的记录

systemctl restart nftables          #重新启动服务

systemctl status nftables           #查看状态
```
