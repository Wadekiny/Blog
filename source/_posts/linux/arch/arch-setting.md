---
title: Arch Linux 的一些设置
mathjax: true
tags: [linux, arch]
date: 2023-01-13 20:24:01
categories: linux
description: arch的一些设置，软件问题和设置
---

# pacman设置

```
-S 指令
安装
sudo pacman -S #安装软件
sudo pacman -Sy #获取最新的软件情况，如果已经是最新了，直接会提示已经更新到最新了。
sudo pacman -Syy #强行更新你的应用的软件库（源）
sudo pacman -Su #更新所有软件
sudo pacman -Syu #更新软件源并更新你的软件
sudo pacman -Syyu #强行更新一遍，再更新软件

查询一个软件
sudo pacman -Ss <pkg_name> #查询所有软件名里面带有<pkg_name>相关的软件。并且查询名支持正则表达

删除软件/var目录下的缓存
sudo pacman -Sc

-R 指令
sudo pacman -R <pkg_name> #删除软件
sudo pacman -Rs <pkg_name> #删除软件，并删除<pkg>所有的依赖包
sudo pacman -Rns <pkg_name> #删除软件，并删除<pkg>所有的依赖，并删掉<pkg>的全局配置文件。 推荐！！

-Q 指令
sudo pacman -Q #显示出所有软件 sudo pacman -Q | wc -l 查询数量
sudo pacman -Qe #查询所有自己安装的软件
sudo pacman -Qeq #查询所有自己安装的软件，只显示包名，不显示版本号等
sudo pacman -Qs <pkg_name> #查询本地安装的所有带<pkg_name>的软件
sudo pacman -Qdt #查询所有孤儿软件，不再被需要的。
sudo pacman -Qdtq #查询所有不再被依赖的包名
```

## 添加中文社区源
1. 找到`/etc/pacman.conf`
2. 结尾添加：
```
[archlinuxcn]
Server =  https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```
3. 刷新数据库`sudo pacman -Syu`后`sudo pacman -S archlinuxcn-keyring`

## 更换镜像源
1. 找到`/etc/pacman.d/mirrorlist`
2. 添加`Server = https://mirrors.aliyun.com/archlinux/$repo/os/$arch`
3. 更新数据库`sudo pacman -Syu`

# AUR 和 yay
使用AUR包有两种方法：
- 克隆仓库，进入仓库目录，`makepgk -si`
- 使用`yay`

# 驱动
    1. CPU编码
    ```
    pacman -S intel-ucode    (intel的cpu装这个)
    pacman -S amd-ucode    (amd的cpu装这个)
    ```
    2. 显卡驱动

    ```
    pacman -S xf86-video-intel（Intel集成显卡驱动，用Intel核显就装，否则不用装）
    pacman -S xf86-video-amdgpu (AMD集成显卡驱动，用amd显卡的就装)
    pacman -S mesa nvidia(-lts) nvidia-settings nvidia-dkms nvidia-utils nvidia-prime（nvidia显卡驱动，用nvidia显卡就装，否则不用装）
    ```
    3. 声卡驱动(忘了怎么装得了)，和dwm里的快捷键要对上，快捷键才能用
    ```
    pacman -S alsa-utils pulseaudio pulseaudio-alsa pulseaudio-bluetooth
    ```
    > 其他资料中(我没写进去)：
    >输入“vim /etc/modprobe.d/disable_dmic.conf”，把下面的文字打进去，保存: 
    >`options snd_hda_intel dmic_detect=0` 

    4. 网卡驱动
    - thinkbook14p(amd)版本的网卡：realtek rtl8852be wifi 6 802.11ax pcie adapter
    - 驱动地址：https://aur.archlinux.org/packages/rtw89-dkms-git
    - `yay -S rtw89-dkms-git`

    5. 设置亮度
    - root用户下，`sudo echo 50 > /sys/class/backligh^Cmdgpu_bl0/brightness`
    - sudo 不能获得root用户的所有权限


# 双系统引导

# 软件

## npm fanyi 报错
- https://github.com/afc163/fanyi#error-spawn-festival-enoent
- 安装`sudo pacman -S festival`

## nm-tray
- 网络管理托盘,pacman就可以安装
- ubuntu(gnome)下可以用nm-applet

## 文件夹可视化管理
- nautilus

## pdf查看器
- okular

## 修改光标样式
- https://wiki.archlinuxcn.org/zh-hans/%E5%85%89%E6%A0%87%E4%B8%BB%E9%A2%98
- lxapperance


## fcitx5安装
1. 安装fcitx5
```
sudo pacman -S fcitx5-im fcitx5-chinese-addons fcitx5-qt fcitx5-gtk
```
2. 在`~/.xinitrc`中添加：
```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
export INPUT_METHOD=fcitx
export SDL_IM_MODULE=fcitx
```
3. 添加到dwm的autostart脚本中
```
fcitx5- d &
```
4. 打开`fcitx5-configtool`, 将`Pinyin` 添加到输入法列表当中
5. 安装主题，需要在`fcitx5-configtool`中设置
```
sudo pacman -S fcitx5-pinyin-zhwiki fcitx5-material-color fcitx5-nord
```


## fcitx在终端内不能触发
- 可能是终端的问题,比如kitty,但kitty有个好处是预览图片方便(ranger)
- 在`~/.xinitrc`内，注意顺序
    ```
    export GTK_IM_MODULE=fcitx
    export QT_IM_MODULE=fcitx
    export XMODIFIERS="@im=fcitx"
    ...
    exec dwm
    ```

## fcitx导致xmodmap的设置被重置
- https://wiki.archlinux.org/title/fcitx
- 如果把'.xmodmap'文件放到家目录下，新版(4.2.7之后)的fcitx会读取其内容，并执行
- 如果把'.xmodmap'文件放到其他目录下，xmodmap的效果会被覆盖
- 不仅fcitx会覆盖xmodmap,其他软件也有可能
- 改用xkb命令：`setxkbmap -option "caps:swapescape"`

## flameshot截图不能复制到剪切板
- 直接`flameshot gui`不能复制到剪切板，也不会有托盘图标
- 解决：在dwm的autostart脚本中添加：`flameshot gui`
- 可能还要安装wl-clipboard(vim中md文件快速粘贴图片)
> https://wiki.archlinux.org/title/Flameshot
> https://github.com/flameshot-org/flameshot/issues/2496


