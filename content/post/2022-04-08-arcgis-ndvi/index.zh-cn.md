---
title: Arcgis计算NDVI出现整数型结果的解决办法
author: Chaoseco
date: '2022-04-08'
slug: index.zh-cn
categories:
  - GIS
tags:
  - ArcGIS
description: ''
thumbnail: ''
---

使用Arcgis中的Raster Calculator计算NDVI，或进行其他期望输出结果为小数的栅格计算时，当输入栅格为整数时，会得到整数输出，因而需要对数据类型进行转换。

在进行计算时，应使用float()对输入数据进行转换，如下所示（以NDVI计算为例）：

```toml
(Float("b5") - Float("b4")) / (Float("b5")  +  Float("b4"))
```
b4，b5分别为landsat 8遥感影像的第4和第5波段。