---
title: ranger配置
date: 2021-04-02 12:46:09
tags: [linux,ranger]
categories: linux 
description: ranger配置文件创建，配置ranger
---


# ranger安装

- 方法1: `pip install ranger-fm`
- 方法2: ...

## 建立配置文件

```shell
$ ranger --copy-config=all
```

在`~/.zshrc`中添加（如果用的是bash，就添加到`~/.bashrc`）：

```config
export RANGER_LOAD_DEFAULT_RC FALSE
```

## 配置默认文件编辑器：
在`rifile.conf`中
