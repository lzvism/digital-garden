---
{"dg-publish":true,"permalink":"/4-computer/4-operating-system/4-windows/work-group-and-domain/"}
---

# Work Group
- 工作组应该是 Windows 独有的概念。功能比较基础，当局域网内的电脑过多 Network Device 有几百台设备的图标，想要找到对应的设备比较麻烦，有个工作组就相当于创建了一个父级文件夹。没有什么认证，想换个工作组改下名即可，工作组之间的 PC 地位同等。
- 每个工作组中都可以有 Master Browser，选举产生，维护局域网内的计算机列表，将主机名和 IP 绑定，这和 DNS 服务器有些类似，不过 Master Browser 使用的是 NetBIOS 而非 DNS 协议，除此之外还有几种局域网内用于解析主机名的方式，host 文件、mDNS 协议等，NetBIOS 已经被打上老旧的标签，现在更多还是 DNS 吧。[SMB 最初基于 NetBIOS](https://www.cnblogs.com/bigrabbit/p/3910094.html) 。
# Domain
- 从主机名到 IP，再 DNS 协议？Work Group 接触的不多，但是 DNS 解析域名这个熟悉啊，Windows 中也有域，是否有什么关联？
- 查看 Windows 域的介绍，域相对宽松随意加入的工作组由域控制器来统一管理，而域控制器是一台 Windows Server 服务器，检查登陆账号允许访问等。
- 在 [这篇Windows Server 2008 R2创建域控的博文](https://www.cnblogs.com/lsdb/p/11412472.html)和[这篇 Windows Server 2012 R2 创建域控的博文](https://blog.csdn.net/qq_28205153/article/details/113827476)中可以看出域名用.划分层级，可命名为 `test.com` 也可命名为 `test.local`，在 2012 的博文中看到域的 NetBIOS 名称为 TEST ，在 DNS 中如果服务器名为 server，那它的完整域名就是 `server.test.local` ，在服务器端创建域用户 pc 或者使用本地管理员的账户通过验证域管理账号密码加入，他的域名就是 `pc.test.local`。域用户(相对的本地用户)登陆电脑通过 DNS 服务获取 IP 就可以互相访问使用资源了。
- 到这里，Windows 域和常提到的域名，在使用上就是顶级域名的不同啊。
