---
title: linux设置代理,git加速
mathjax: true
tags: [linux, network, proxy, git]
date: 2023-01-13 16:29:37
categories: linux
description: 
---


# 安装代理软件

- qv2ray 或 clash for windows(linux版本)

## qv2ray

### 第一步，安装Qv2ray

### 第二步，安装V2ray Core

- 选择 v2ray-linux-64.zip
https://github.com/v2fly/v2ray-core/releases

### 第三步，设置Qv2ray

1. 做好类似于下图的设置，检查v2ray core和系统时间 
    ![qv2ray-setting](./proxy-md/qv2ray-setting.png)

2. 添加订阅
    ![subscribe](./proxy-md/subscribe.png)

### 第四步，qv2ray内启动代理

## Clash for Windows

### 第一步 在'Profiles'里添加订阅
### 第二步 在'Proxies'里选择Rule,自动选择
### 第三步 Clash的linux版本打开自动启动代理

# 设置系统代理

如果只是启动了软件的代理，系统的流量并没有从代理的端口走，还是不能git加速。

- 对于终端，要设置环境变量才能走代理`export all_proxy=socks5://127.0.0.1:7890`
- 对于gnome桌面，有系统的手动代理管理
- 对于git，在`~/.gitconfig`中设置：
```
[http]
   proxy = socks5://127.0.0.1:7890
[https]
    proxy = socks5://127.0.0.1:7890
```

