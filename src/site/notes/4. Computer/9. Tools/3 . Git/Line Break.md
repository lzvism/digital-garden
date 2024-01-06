---
{"dg-publish":true,"permalink":"/4-computer/9-tools/3-git/line-break/"}
---

# What
Obsidan push 失败，往回查找发现 add 也不行，无法 merge，最后定位到是换行符的问题，猜测是我跨平台修改同步后导致的问题。
# Why
换行和回车是不同概念
- 回车(纸车)：CR(carriage return), return oldline begin, `\r`, ASCII=13(`\x0d`)
- 换行：LF(line feed), newline begin, `\n`, ASCII=10(`\x0a`)
这两个说法源于机械打字机，到了计算机时代为了节省字符，在不同的操作系统上
- Unix/Linux 系统里，每行结尾只有"<换行>"，即"`\n`"； 
- Windows 系统里面，每行结尾是"<回车><换行>"，即"`\r\n`"； 
- macOS 系统从 X 后，CR 修改为了 LF 和 Linux 一致
因此 Linux 的文件在 Windows 是一行，Windows 的文件在 Linux 中末尾会多出 `^M` (Linux 用 `^M` 表示回车符 `\r`)
# How
在 git 中添加参数
```
// 提交时转换为LF，检出时转换为CRLF
git config --global core.autocrlf true 
```


[\\r \\n 回车换行符详解-CSDN博客](https://blog.csdn.net/lqy971966/article/details/108355292)
[Git自动换行符 - 简书](https://www.jianshu.com/p/f13ef9e538e0)
[Git 多平台换行符问题(LF or CRLF)](https://kuanghy.github.io/2017/03/19/git-lf-or-crlf)