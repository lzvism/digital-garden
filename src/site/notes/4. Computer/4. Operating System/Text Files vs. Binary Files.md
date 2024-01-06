---
{"dg-publish":true,"permalink":"/4-computer/4-operating-system/text-files-vs-binary-files/"}
---

[文本文件与二进制文件的区别\_文本文件与二进制文件读写的根本区别-CSDN博客](https://blog.csdn.net/xufox/article/details/82800685)
- 从本质上来看，文件存储在硬盘中都是二进制的 0101010，所以文本文件也是二进制文件。应该都有这样的经历，用 Notepad 打开一个未知的文件或者一个 TXT 文件，成功打开了文件但是内容全是乱码。这是因为 Notepad 打开一个文件的逻辑是将固定数量的 bit 进行解码，比如纯英可以只用 ASCII 码，每 Byte 解码为一个字符。
- 测试新建一个文本文件，5 个数字正好占用 5Bytes ![image.png](https://lsky.lzism.top:8167/i/2023/12/31/202312311120029.webp)


