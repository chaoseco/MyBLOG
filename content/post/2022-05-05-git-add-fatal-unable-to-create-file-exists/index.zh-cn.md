---
title: 'git add - fatal: Unable to create: …File exists'
author: ChaosEco
date: '2022-05-05'
slug: index.zh-cn
categories:
  - Git
tags:
  - Git
description: ''
thumbnail: ''
---

#### 报错信息如下：

```bash
$ git add --all
fatal: Unable to create 'E:/OneDrive/Mine/MySite/MyBLOG/.git/index.lock': File exists.

Another git process seems to be running in this repository, e.g.
an editor opened by 'git commit'. Please make sure all processes
are terminated then try again. If it still fails, a git process
may have crashed in this repository earlier:
remove the file manually to continue.
```

#### 解决方案
```bash
$ rm -f ./.git/index.lock
```