---
title: How to beautify our blog
date: 2025-06-26 17:42:33
tags: blog
---

install hexo according to the following documentation and initialize our blog

https://hexo.io/zh-cn/docs/

mofigy site config.yml to set the theme for our blog

```shell
git clone git@github.com:theme-next/hexo-theme-next.git themes/next
#cofig.yaml
theme: next
```

Execute the following command to start our website

```shell
hexo clean
hexo g
hexo s
```

