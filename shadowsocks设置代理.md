shadowsocks-qt5 GUI 客户端下载地址汇总：
https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation

CentOS7 版本下载地址：
https://copr.fedorainfracloud.org/coprs/librehat/shadowsocks/repo/epel-7/librehat-shadowsocks-epel-7.repo


```
yum install epel-release

cd /etc/yum.repos.d/
wget https://copr.fedorainfracloud.org/coprs/librehat/shadowsocks/repo/epel-7/librehat-shadowsocks-epel-7.repo
yum install shadowsocks-qt5
```

shadowsocks-qt5设置：
根据vps填写 服务器地址，服务器端口，密钥，加密方式
本地地址：127.0.0.1，本地端口：1080，本地服务器类型：SOCKS5

Firefox浏览器设置代理：
设置->网络->手动配置代理->SOCKS主机-> 127.0.0.1，1080，SOCKSv5

terminal 设置代理：

```
yum install privoxy
vim /etc/privoxy/config  # 添加   forward-socks5 / 127.0.0.1:1080 .     注意保留最后那个点号

systemctrl start privoxy.service

export http_proxy='http://127.0.0.1:8118'
export https_proxy='http://127.0.0.1:8118'

curl -I  www.google.com # 测试一下
```
