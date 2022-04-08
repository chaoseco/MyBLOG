---
title: 'How To: Create sequential numbers in a field using Python in the Field Calculator'
author: Chaoseco
date: '2022-04-08'
slug: sequential-numbers
categories:
  - GIS
tags:
  - ArcGIS
description: ''
thumbnail: ''
---
1 Create a new short integer field.

2 Right-click the new field and select Field Calculator.

3 Set the Parser to Python.

4 Check the check box for Show Codeblock.

5 Paste the following into the Pre-Logic Script Code:

```python
rec=0
def autoIncrement():
 global rec
 pStart = 1
 pInterval = 1
 if (rec == 0):
  rec = pStart
 else:
  rec += pInterval
 return rec
```
 
6 Paste the following code in the smaller box below the Pre-Logic Script Code:
 
```python
autoIncrement()
```
 
7 Click OK. 
 
 Source:
[[Source 1](https://support.esri.com/en/technical-article/000011137)]