---
title: Matlab spatial panels - Reference to non-existent field 'parm'
author: Chaoseco
date: '2022-04-08'
slug: spatial-panels
categories:
  - Spatial Analysis
tags:
  - Matlab
  - Spatial panels
description: ''
thumbnail: ''
---

这个问题是由于matlab引用的文件中缺失对参数‘parm’的定义造成的。

新版的jplv7工具箱中sar_panel_FE.m没有定义result.parm，可以找到旧版的sar_panel_FE.m文件放入Elhorst文件夹，由于在路径设置中，Elhorst文件夹在jplv7文件夹之前，所以在读取顺序上旧版的sar_panel_FE.m文件会覆盖jplv7文件夹中的新版文件。

[[Source](http://bbs.pinggu.org/thread-3661610-1-1.html)]