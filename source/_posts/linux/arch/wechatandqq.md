---
title: Arch Linux 下wechat和qq的安装
mathjax: true
tags: [linux, arch, wechat, qq]
date: 2023-01-15 00:41:01
categories: linux
description: arch下解决wechat和qq
---

# 打开`multilib`

否则会报错：
```
warning: cannot resolve "lib32-fontconfig", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-lcms2", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libxml2", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libxcursor", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libxrandr", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libxdamage", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libxi", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-gettext", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-freetype2", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-glu", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libsm", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-libpcap", a dependency of "wine-for-wechat"
warning: cannot resolve "lib32-faudio", a dependency of "wine-for-wechat"
```

1. 在`/etc/pacman.conf`中去掉下面两行的注释
```
[multilib]
Include = /etc/pacman.d/mirrorlist
```

2. 执行`sudo pacman -Syu`

> https://blog.csdn.net/weixin_52027058/article/details/128346840


# 微信

```
yay -S deepin-wine-wechat
```

## 可能遇到的问题

1. 窗口周围出现奇怪的黑色或透明边框 只需要修改 
```
/opt/apps/xxx/files/run.sh 中的 
export APPRUN_CMD="deepin-wine6-stable"
变更为
export APPRUN_CMD="deepin-wine5"
```

## 固定软件包的版本：
```
编辑 /etc/pacman.conf

IgnorePkg = deepin-wine-wechat 
```

> https://github.com/vufa/deepin-wine-wechat-arch#%E4%BB%8Eaur%E5%AE%89%E8%A3%85
> https://www.bilibili.com/video/BV1Z3411F7TL/?spm_id_from=333.337.search-card.all.click&vd_source=c59669dc10d72873dc1a840e4c9b6095



# QQ

## icalingua++

https://github.com/Icalingua-plus-plus/Icalingua-plus-plus

## linuxqq
启动很慢，有时候会卡住
```
yay -S linuxqq
```
https://im.qq.com/linuxqq/index.shtml
