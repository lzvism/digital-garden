---
{"dg-publish":true,"permalink":"/4-computer/4-operating-system/2-unraid/windows-vm-network-file-share/","tags":["Issue","Windows"]}
---

# What
在网络共享中可以看到有我的 Unraid 服务器，有时打不开并提示 ![image.png|601](https://lsky.lzism.top:8167/i/2023/12/27/202312271256506.webp)
但是可以通过 IP 添加 Network Location，而第三方软件选择下载路径的时候又无法选择 map 的文件夹
# Why
- 搜索时发现和我一样的情况没有解答，但是扩展了关于 Windows 的一个 BUG，[Windows 不允许使用不同的用户名来多次连接到同一个服务器](https://post.smzdm.com/p/a7dmllm9/)，在 Network and Device 中访问网络共享文件夹时，如果是 public folder， Windows 使用本机名称\\用户名的身份和密码访问，成功后会缓存证书，不过服务器上的 samba 将其归为 nobody 用户，而访问 private folder 会被要求输入账号密码，这就是第二个身份了。如果同时访问 Public 和 Private，将会是两个身份访问同一个服务器，Windows 不允许这样的访问。这种情况有几种解决方法
	1. 在 Network and Device 中访问时，服务器地址为主机名，如果使用 ip 就会被判断为不同的服务器
	2. 先访问 Private Folder 缓存证书后，Windows 在访问 Public 文件夹时会直接使用已有证书，那就是同一个身份
	3. Windows 的访问流程就是第一次访问获取认证后，以后的访问直接使用证书，所以也可以直接先添加 Private Folder 的凭证
- Windows 是怎么通过主机名访问的？主机名和域名一样需要解析为 IP 地址，具体的实现 [LLMNR 等协议](https://www.cnblogs.com/real-bert/p/15852377.html)太底层不研究了，使用 ping 和 nslookup 可以测试主机名的解析，有的主机名解析既有 IPv4 也有 IPv6 地址可以指添加命令行参数指定协议，如
	- `ping -4 tower`
	- `nslookup -type=A tower`
	猜测我遇到 cannot access 就是因为主机名解析，但是这个问题现在没有保持出现，无法判断了。
- 我原本以为第三方下载软件无法选择 map 的文件夹和上面是绑定的问题，后面谷歌出是权限的问题，管理员权限无法访问网络映射盘。有点反直觉啊，管理员权限应该是更高的权限反而不能访问低的？Linux 里有了管理员权限为所欲为嘞。大佬的解释是 windows 不允许从低级别向高级别发送调用命令，映射的文件无法使用管理员权限的应用来显示？
# How
- [SMB Problem (Cant access \\Hostname, 0x80070035) - General Support - Unraid](https://forums.unraid.net/topic/50911-smb-problem-cant-access-hostname-0x80070035/) 
- [win10管理员权限无法访问网络映射盘？ - 知乎](https://www.zhihu.com/question/48282477)，重新 net use
- [zz: virsual studio等AP无法访问网络映射驱动器(netmap drive)的解决办法\_vs 读不到网络驱动盘-CSDN博客](https://blog.csdn.net/jtujtujtu/article/details/51122303)
- [virsual studio等AP无法访问网络映射驱动器(map network drive)的解决办法（二） - CodeAntenna](https://codeantenna.com/a/lptzKdQLWr)