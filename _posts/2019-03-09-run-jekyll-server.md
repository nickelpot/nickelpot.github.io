---
layout: post
title: Can Not Find Jekyll Command On Terminal
description: 
modified: 2019-03-09
tags: [Jekyll, macOS, memo]
image:
  path: /images/title-background-4.jpg
  feature: title-background-4.jpg
  credit: Nickelpot
  creditlink: https://nickelpot.github.io
---

When I installed Jekyll and other gems, I changed my gem path.

```bash
$ export GEM_HOME=$HOME/gems
$ export PATH=$HOME/gems/bin:$PATH
```

After set everything, when I start new terminal and run Jekyll server, I get this message.

```bash
-bash: jekyll: command not found
```

I set again gem path and try Jekyll server. It works well.

```bash
$ jekyll serve
```