---
layout: post
title: Sublime Text 3 的Nodejs插件
pid: 100
tags: [Sublime, Nodejs]
---

在使用Sublime Text 3开发Nodejs程序的时候，我们需要安装Nodejs的插件。可以按照以下步骤来操作。

# 下载插件

	git clone https://github.com/tanepiper/SublimeText-Nodejs "%APPDATA%\Sublime Text 3\Packages\Nodejs"

# 修改配置
C:\Users\baoguo\AppData\Roaming\Sublime Text 3\Packages\Nodejs\Nodejs.sublime-build

	{
	  "cmd": ["node", "$file"],
	  "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
	  "selector": "source.js",
	  "shell":true,
	  "encoding": "cp936",
	  "windows":
	    {
		"cmd": ["taskkill", "/F", "/IM", "node.exe","&","node", "$file"]  
	    },
	  "linux":
	    {
		"cmd": ["killall node; node", "$file"]
	    }
	}

修改完成后，记得重启Sublime Text 3.

# 常用命令

	Ctrl+B //运行
	Tools/ Cancel Build(Ctrl+Break)
