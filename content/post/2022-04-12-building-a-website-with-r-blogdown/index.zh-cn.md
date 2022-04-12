---
title: Building a website with R Blogdown
author: ChaosEco
date: '2022-04-12'
slug: building-a-website-with-r-blogdown.zh-cn
categories:
  - R
tags:
  - blogdown
description: ''
thumbnail: ''
---

##### 1. 创建Github repository

+ 前往<https://github.com/>,登陆账户，如下创建新的repository：

  ![](/Blogdown/1.png "登陆Github")

  ![](/Blogdown/2.png "创建repo")

+ 之后，记录下新建repo的URL后续使用。

  ![](/Blogdown/3.png "repo url")

##### 2. 构建RStudio-Github链接

- 打开Rstudio，选择File->New project，随后进行如下操作：

  ![](/Blogdown/4.png "new project with git 1")

  ![](/Blogdown/5.png "new project with git 1")

  ![](/Blogdown/6.png "new project with git 1")

##### 3. 安装Blogdwon, Hugo

- 在Rstudio中运行如下代码：
  ```r
  install.packages("blogdown")
  library(blogdown)
  blogdown::install_hugo()
  ```

##### 4. 创建网站
- Rstudio中运行如下代码：
  ``` r
  blogdown::new_site(theme = "Vimux/Mainroad") # theme可根据个人喜好修改
  ```
- 完成后，使用以下命令检查新建网站是否正常运行：
  ``` r
  blogdown::serve_site()
  ```
- 后续可修改config.toml/config.yaml文件以对网站进行配置修改。

##### 5. 使用Git管理网站更新

- 可在Rstudio或Git bash中管理网站更新，Rstudio中可如下图对更新进行commit和push：

  ![](/Blogdown/7.png "commit push with Rstudio")

- 此外，也可在git bash中对更新进行管理（此方法一般会比Rstudio中速度快些），具体如下：
  - 首先，通过cd命令将工作路径切换到网站本地文件夹
  - 随后，逐步运行如下命令：
    ``` toml
    git status  # To see what’s going on with the files in your repository
    git add --all # Add the files to be tracked
    git commit -m "first commit/Whatever u want" # Commit file changes
    git push # Push files to Github
    
    ```
    PS: git使用`git commit`命令后显示Author identity unknown的话，输入以下命令：
    ```toml
    git config user.email "Your email address"
    git config user.name "Yout name"
    ```
  
    此外，运行`git push`后若报错（如下），很有可能是网络不稳定，连接超时导致的，可多尝试几次即可解决
    ```toml
    fatal: unable to access 'https://github.com/chaoseco/MyBLOG/': OpenSSL SSL_read: Connection was reset, errno 10054
    ```

##### 6. 在Netlify上部署
- 前往<https://app.netlify.com/>，可通过GitHub登陆；
- 登陆后，选择Create a new site 或 Add new site (以下以Add new site为例)；
- 如下，选择Import an existing project;
  ![](/Blogdown/8.png "Import an existing project")
  
- 随后，依次如下操作：
  ![](/Blogdown/9.png "9")
  ![](/Blogdown/10.png "10")
  ![](/Blogdown/11.png "11")

- 最后，设置域名及DNS
  ![](/Blogdown/12.png "12")

[[Source](https://www.storybench.org/how-to-build-a-website-with-blogdown-in-r/)]