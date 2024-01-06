---
{"dg-publish":true,"permalink":"/4-computer/4-operating-system/environment-variable/"}
---

[简单易懂解说「到底什么是环境变量？」| Code | Chihokyo BLOG | 旺财的博客](https://chihokyo.com/post/6/)
- 学了一点编程，变量的概念还是比较清晰的，存储一些值，一个变量有它的有效范围，所以还有全局变量这个能从任意位置调用的存在。从一段代码的小程序到操作系统这个大程序，环境变量相当于一个从任意位置调用的全局变量。
- 一般用到 Windows 环境变量是安了某某软件后需要在 PATH 中添加程序的位置，比如 安装完 Python 需要添加环境变量，即可调用解释器或者相关工具。
- Linux 输入一个命令可以被执行，比如 `ls`，它本质是一个可执行文件，在 `/usr/bin` 中，也是 PATH 环境变量的功劳。