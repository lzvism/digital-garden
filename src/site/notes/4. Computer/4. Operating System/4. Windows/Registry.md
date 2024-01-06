---
{"dg-publish":true,"permalink":"/4-computer/4-operating-system/4-windows/registry/"}
---

[注册表是什么？怎么修改？\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV11Y4y1n7wY/?spm_id_from=333.337.search-card.all.click&vd_source=0e8d5a2d613f40b7bb080c0607a88b1e)
[【科普】什么是注册表？如何查看、备份、导入、修改注册表？\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV1t34y1F79B/?spm_id_from=333.337.search-card.all.click&vd_source=0e8d5a2d613f40b7bb080c0607a88b1e)
[Windows Registry - Wikipedia](https://en.wikipedia.org/wiki/Windows_Registry)
[【科普】导入Windows注册表会让你系统崩溃的真正原因-2021重制 正确备份方法-导入避雷操作\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV1pA41137rp/?vd_source=0e8d5a2d613f40b7bb080c0607a88b1e)

一句话：注册表是存放软件、系统配置信息的数据库。
在 Windows 95 和 Windows NT 中将原本散落在各处的 .ini 文件(Initialization 初始化，是文本文件)记录的配置集中到了注册表中。注册表的数据文件在 `C:\Windows\System32\config` 只能通过 Regedit(Registry Editor，在 `C:\Windows`)打开。注册表的基本概念为 key、subkey、value。可以通过注册表实现，添加选项到文件管理器的右键菜单 Context Menus，让任务栏的时间显示秒等等
注册表可以导入导出，默认的全部导出只能导出 HKEY_LOCAL_MACHINE 和 HKEY_USERS 两条主键，不要直接导入，导入是危险操作，导入注册表文件不会删除项和值，不是还原。

很少动注册表，了解即可。