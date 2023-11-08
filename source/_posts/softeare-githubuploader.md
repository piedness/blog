---
title: "一键生成hexo blog文件夹并上传到GitHub仓库"
date: 2023-10-26 17:23:31
category: 软件
---

> 使用场景：
1. 用编辑器（例：sublime）完成对Hexo blog根目录文件的修改。
2. 使用Hexo_githubpage_uploader一键完成hexo clean、hexo g命令。
3. 使用该软件一键完成将本地blog/public文件夹下所有文件同步至相应GitHub仓库。

> 需求：
1. 登录Github
	1. 输入框
	2. 登入button
2. 选择Github仓库
	1. 下拉框
	2. 确认选择button
3. 选择本地blog根目录
	1. 输入框
	2. 确认选择button
4. 一键完成hexo clean、hexo g、hexo s命令的button，并跳转浏览器打开（可选框）
5. 一键同步button

> 所用开发软件：visual studio

> 是否开源：否

> 设计语言：fluent 2