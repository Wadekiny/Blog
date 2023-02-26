---
title: asd2num
mathjax: true
tags: [linux, wayland, hyprland, asd2num]
date: 2023-02-03 13:18:38
categories: linux
description: hyprland(wayland) 下通过shift_r键开启ASD2NUM模式(数字键搬到键盘中间一行)
---

# 安装 keyd 工具

> github地址: https://github.com/rvaiya/keyd
1. `yay -S keyd`
2. 添加默认配置文件`/etc/keyd/default.conf`，因为 keyd 默认将 rightshift 映射到了 leftshift，所以要改回来

```conf
[ids]

*

[main]

rightshift = rightshift

```

## 测试 keyd

1. 修改`/etc/keyd/default.conf`
```
[ids]

*

[main]

rightshift = rightshift

a=1
1=a
```

2. 启动keyd `sudo systemctl start keyd`, 如果是`sudo systemctl enable keyd`就会设置成开机启动
3. 完事之后关掉 keyd `sudo systemctl stop keyd`

# 用python脚本实现 rightshift 切换功能

1. 通过evdev库捕获键盘事件
2. 更新asd2num_flag
3. 执行系统命令`keyd -e <expression>` 来更改映射(因为官方给的reload功能用不了)
4. 将当前的状态写入到文件中，用来个waybar读取
5. 发送 signal 给 waybar ，更新 waybar 的显示


# waybar设置

config 中添加`custom/asd2num`并设置


# hyprland设置

设置自动启动python脚本


