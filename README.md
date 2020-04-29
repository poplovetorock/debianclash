# debianclash
Modified shell scripts of Clash client for Debian10. Refer to Youtuber Miyue`s DTshell script、yuanlam and A-wing blog.

#Tested: Debian 10.3

#Attention： Please be root to run scripts and reboot after installation. Then just wait till unbound installed for about 1~2 minutes.

There`re two options for you to choose.

*Option 1: using redir-host for clash DNS mode.
```
apt install wget -y
```

```
bash <(wget --no-check-certificate -qO- https://raw.githubusercontent.com/poplovetorock/debianclash/master/1key)
```

*Option 2: using fake-ip for clash DNS mode.
```
apt install wget -y
```

```
bash <(wget --no-check-certificate -qO- https://raw.githubusercontent.com/poplovetorock/debianclash/master/1key_fakeip)
```
Clash command
```
http://your ip:9090/ui/                  #dashboard web
http://your ip:8000                      #control panel(admin  123456)
/home/clash/.config/clash/config.yaml    #config
```

Smartdns command

```
systemctl restart smartdns          #restart service

systemctl status smartdns           #check status
```
unbound command
```
systemctl restart unbound           #restart service

systemctl status unbound            #check status
```
nftables command
```
nft flush ruleset                   #flush ruleset

nft -f /etc/nftables.conf           #start new ruleset

nft list ruleset                    #check ruleset list

systemctl restart nftables          #restart service

systemctl status nftables           #check status
```
