---
title: dwm
mathjax: true
tags: [linux,dwm]
date: 2023-01-12 13:34:38
categories: linux
description: 使用dwm期间遇到的一些小问题
---

# autostart.sh 脚本(arch下)

```
#! /bin/bash
# sudo systemctl start todeskd.service

nm-tray &
flameshot &
setxkbmap -option "caps:swapescape"
dunst &
fcitx5 -d &
/home/wadekiny/ProgramFiles/picom/build/src/picom &
feh --bg-fill ~/Pictures/background/bg0.jpg  &
bash /home/wadekiny/ProgramFiles/dwm-wadekiny/statusbar/statusbar.sh cron &
bash /home/wadekiny/Scripts/tap2click.sh &
bash /home/wadekiny/Scripts/inverse-scroll.sh &
#bash /home/wadekiny/Scripts/xmodmap/esc2capslock.sh &
#python3 /home/wadekiny/Scripts/wallpic.py &
#nm-applet &
#picom -b &
#/home/wadekiny/ProgramFiles/picom-wadekiny/build/src/picom --experimental-backends &
```

# 显示窗口信息的方法
- 命令`xprop` (用来获取class,name之类的属性)
- 命令`xwininfo`


# 有时候statusbar不能显示
- 是因为temp文件中多了一些奇奇怪怪的东西，删除即可

# statusbar日期点开之后显示异常
- 输入`cal`命令，今天的日期会被高亮，而notify-send的语法不能识别这个高亮的修饰符
- 解决办法：statusbar日期脚本中,使用正则表达式替换高亮修饰符号(要考虑到所有情况，替换为空还是空格......)
    ```
    cal | sed 's/_^H/ /' | sed 's/  _^H/>/' 
    # ^H的编码:0x8
    ```

# 通过按F9自动输入密码
- (使用NOPASS已经用不上这个功能了)

1. dwm的配置头文件中添加快捷键
2. 快捷键调用scripts中的auto_type.py



# 如何启动dwm
- 有登陆管理器
    - 添加文件：/usr/share/xsession/dwm.desktop，内容忘了怎么写
- 修改~/.xinitrc
    - 添加`exec dwm`
    - 这样`startx`之后就可以启动dwm

