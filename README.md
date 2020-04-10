# debianclash
参照油管UP主(米月大佬)灯脚脚本、yuanlam以及A-wing blog修改的一键安装Clash For Debian10。自用。。。

#支持Debian 10（其他系统未测试）

##脚本使用注意事项：

脚本需在root用户下执行
Clash使用redir-host的DNS模式，不喜勿用
```
apt install wget -y
```

```
bash <(wget --no-check-certificate -qO- https://raw.githubusercontent.com/poplovetorock/debianclash/1key)
```
Clash管理

http://你的ip:9090/ui/                   #web界面

/home/clash/.config/clash/config.yaml    #配置文件地址


Smartdns、undound、nftables
SmartDNS管理命令
```
systemctl restart smartdns          #重新启动服务

systemctl status smartdns           #查看状态
```
unbound管理命令
```
systemctl restart unbound           #重新启动服务

systemctl status unbound            #查看状态
```
nftables命令
```
nft flush ruleset                   #清空设置

nft -f /etc/nftables.conf           #使新的设置生效

nft list ruleset                    #查看当前 nftables 的记录

systemctl enable nftables           #查看状态

systemctl restart nftables          #重新启动服务
```
