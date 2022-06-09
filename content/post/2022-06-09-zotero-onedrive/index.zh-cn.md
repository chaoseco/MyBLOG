---
title: Zotero Onedrive云同步
author: Chaoseco
date: '2022-06-09'
slug: zotero-onedrive
categories:
  - Zotero
tags:
  - Syncing
description: ''
thumbnail: ''
---

1. Edit->Preferences->Sync->Setting，注册登陆账号，然后取消勾选“file syncing”的两个选框。

2. Edit->Preferences->Advanced->Files and Folders->Linked Attachment Base Directory，选择OneDrive里的一个文件夹，如：C:\Users\***\OneDrive\Zotero\storage

3. 在Data Directory Location点 "Show Data Directory" (不想放到C盘的可以在这里自定义本地路径（一定要是本地路径，不然容易冲突，如：D:\Zotero）)

4. 打开之后将storage文件夹内容剪切到 C:\Users\***\OneDrive\Zotero\storage，然后删除本地文件里的storage。（如果还没开始存文件的话可能没有storage这个文件夹，可以跳过这一步）

5. 用管理员身份打开cmd，win10直接搜索“cmd”然后右键管理员身份打开。在命令行中输入：
    ```
    mklink /J "D:\Zotero\storage" "C:\Users\***\OneDrive\Zotero\storage"
    ```
6. 第一个地址为本地地址（记得把本地的storage删了，不然可能会报错），第二个为OneDrive地址，注意一定带上引号。如果有自己的第二台电脑也是一样的步骤，不过要先把文件夹链接好，再登录自己的zotero账号开始同步，这样就可以在两台电脑无缝同步啦！

*PS：这里是同步storage（pdf文件等附件）的步骤，如果想同步styles（引用格式）、translators（翻译），将步骤中的storage换成styles/translators即可。*

[[Source](http://me.liuxuan.xyz/archives/981)]