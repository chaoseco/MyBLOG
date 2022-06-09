---
title: Math expression in Mainroad theme
author: Chaoseco
date: '2022-06-09'
slug: math-expression
categories:
  - Blogdown
tags:
  - Math
  - Mainroad
description: ''
thumbnail: ''
---

#### Enabling MathJax in a page (TeX syntax)

Add the following line to `config.toml`:

```toml
[Params]
...
mathjax = true # Enable MathJax
mathjaxPath = "https://cdn.mathjax.org/mathjax/latest/MathJax.js" # Specify MathJax path
mathjaxConfig = "TeX-AMS-MML_SVG" # MathJax config
...
```

At the top of a page where you want to use mathjax, add the following line.
```toml
mathjax = true
```
Then, you can use TeX syntax in the post double dollar mark `$$`.

#### Inline math

Add the following lines in `./layouts/partials/header.html`.

``` html
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
  tex2jax: {
    inlineMath: [['$','$'], ['\\(','\\)']]
  }
});
</script>
```


[[Source](https://atlex00.com/hugo/mainroad/)]
