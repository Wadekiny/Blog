---
title: 报错：dpkg-frontend-is-locked
mathjax: true
tags: [linux, ubuntu]
date: 2022-02-14 12:31:42
categories: linux
description: 
---

- 问题
```shell
$ sudo dpkg -i xxxxx.deb
dpkg: error: dpkg frontend is locked by another process
```
- 解决 
```shell
$ sudo rm /var/lib/dpkg/lock-frontend
```
