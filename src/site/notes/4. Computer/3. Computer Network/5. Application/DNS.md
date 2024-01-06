---
{"dg-publish":true,"permalink":"/4-computer/3-computer-network/5-application/dns/"}
---



ping 不通域名但是可以 ping 通 IP 的时候就需要思考了

[DNS、域、域名及FQDN 概念 - 吴玉祥 - 博客园](https://www.cnblogs.com/wuyuxiang/p/5166653.html)

DDNS 服务

将用户的动态公网 IP 地址映射到一个固定的域名解析服务上，想用这个服务，你得有公网 IP
想在外网访问，你得有个公网 IP 让设备能找到你，如果有个固定的公网 IP 那记 IP 也可以直接访问，嫌 IP 麻烦可以绑定域名，通过域名来访问，但一般人拿不到固定的公网 IP，动态 IP 在变化不好记，只能记域名，通过 ddns 来访问。
注意：DDNS 是在客户机上的端，对应 DNS 服务器

A 记录


[阿里云域名修改 DNS 服务器或添加域名解析并解析到搬瓦工 VPS 教程 - Bandwagonhost中文网-Bandwagonhost中文网](https://www.bandwagonhost.net/6192.html)