---
title: TODO
mathjax: true
tags: [todo]
date: 9000-01-01 22:50:05
categories: todo
description: todo list
---



目的：
回归3dmm参数生成大致shape和texture
学习text2face的方法，分开面部部件，shape上分开？分开才能精细可控
hair eye
额外的uv图用来恢复高清细节
模型去除光照渲染
反射率之类的东西
部件gcn
meshgcn
粗-细
眼镜
舞蹈和人脸合成一起
纹理细节为什么不好？
expgan



## vim:
vim 如何在浮动窗口和普通窗口切换
neovide can implement cursors smooth but can not input Chinese
vim:hex 16进制表示方法
:set laststatus=2
`:set statusline=%<%f%h%m%r%=%b\ 0x%B\ \ %l,%c%V\ %P`
vim 正则表达式替换
mason 不能安装python-lanuage-server https://www.saoniuhuo.com/question/detail-2133503.htmlcli

## network
wsl代理需要设置防火墙- ip到底是哪个？
easyconnect 打开导致不能git push

## python
16. pynput need sudo apt install python3-tk python3-dev
17. pyautogui 可以弹窗
pyright opencv
import pyautogui
显示一个简单的带文字和OK按钮的消息弹窗。用户点击后返回button的文字。
pyautogui.alert(text='', title='', button='OK')
pysocket
proxy打开后，pip install报错 https://blog.csdn.net/tuzixini/article/details/88203910
pip 换源



## xorg
Xresources修改dpi？
https://zhuanlan.zhihu.com/p/513859236
2. Xauthority should be wadekiny's, instaed, login loop
.Xresources 
.xinitrc
免密自动登录 startx
xorg 缩放倍数
xrandr --output e-DP1 --scale 0.5x0.5
arch无法识别typec接口显示器

## driver
3. Nvidia driver should be 470.xxx. or black screen




## linux
从archlinux.md中拆分 profile bashrcxxxxx优先级，形成一篇新的
~/.fonts/ 添加字体文件，可以直接安装字体
grub不能识别windows
挂载windows分区https://zhuanlan.zhihu.com/p/513859236




## zotero
zotero
坚果云 zotero




## hexo
hexo deploy github
hexo 相对位置文件路径
hexo next  搜索


wechat udis86


waybar sound network
wayland network : exex nm-applet --indicator
> https://github.com/swaywm/sway/issues/1357#issuecomment-894436375

截图：grimshot脚本

obs need qt6-wayland
obs在屏幕缩放为2时报错不能启动
nvim 的dap vscode-cpp程序位置
g++ -g 生成调试信息 -o 输出文件名
vim 内置终端样式 cursor 好像还改不了
https://github.com/neovim/neovim/issues/3681

firefox 设置全屏不隐藏标签栏目
https://blog.csdn.net/dongzhiquan/article/details/6245732

arch蓝牙
mark.vim

高亮选中单词



vim 代码模板
vim clang-format自定义格式

cpp调试去掉选项2

vim 中间一排数字键
 rockerBOO /awesome-neovim 有一些插件

 vimscript字符串替换 substitute
 https://blog.csdn.net/smstong/article/details/20791329

 vim redraw

 select mode
 visual mode
 modemap -x

 vim 导出map

 psmr 30

 sudo waydroid init
 [22:03:12] Failed to load binder driver
[22:03:12] modprobe: FATAL: Module binder_linux not found in directory /lib/modules/5.15.90-1-lts
[22:03:12] ERROR: Binder node "binder" for waydroid not found
[22:03:12] See also: <https://github.com/waydroid>
Run 'waydroid log' for details
https://github.com/waydroid/waydroid/issues/535
> yay -S anbox-modules-dkms-git


waydroid init下载速度太慢，手动下载
https://github.com/waydroid/waydroid/issues/215
注意要下载两个压缩包，并解压


hyprland wlogout

swaylock-effect


wayland键盘映射
https://github.com/KarsMulder/evsieve
> https://wiki.archlinux.org/title/Input_remap_utilities

https://python-evdev.readthedocs.io/en/latest/install.html
先修改event的读写权限(用户所在组)
> https://github.com/k0kubun/xremap
https://cloud.tencent.com/developer/article/1725906
https://learnku.com/articles/31223
https://www.myfreax.com/how-to-add-user-to-group-in-linux/

cava 显示音乐波形
tty-clock

类似资源管理的东西 btop

neovide： WINIT_UNIX_BACKEND=x11 neovide但是仍然不能使用fcitx

pip 安装的kbmap,运行提示Traceback (most recent call last):
  File "/home/wadekiny/.local/bin/kbmap", line 2, in <module>
    from kbmap.kbmap import main
  File "/home/wadekiny/.local/lib/python3.10/site-packages/kbmap/kbmap.py", line 6, in <module>
    import pkg_resources
ModuleNotFoundError: No module named 'pkg_resources'


解决：pip install setuptools






















nerf:
NeRFFaceEditing: Disentangled Face Editing in Neural Radiance Fields



1. img+audio drive  nerf
dfa-nerf
ad-nerf

2. img+text drive nerf
Nerf-Art
Zero-Shot Text-Guided Object Generation with Dream Fields
clip-nerf
coc virtual text






# 流程







项目问题 堆栈溢出
ulxxx命令查看

waybar-hyprland-git
https://aur.archlinux.org/packages/waybar-hyprland-git


新版waybar好像取消了其他模块的hover功能,换回之前commit的那个版本
对于hyprland,在编译waybar时,需要
https://github.com/Alexays/Waybar/issues/1640#issuecomment-1278519500
否则回unknowmodule wlr/workspaces
解决


clone下来的waybar不能点击切换workspace,因为默认没有调用hyprctl dispatch workspace ...
用waybar-hyprland-git中的
    sed -i 's/zext_workspace_handle_v1_activate(workspace_handle_);/const std::string command = "hyprctl dispatch workspace " + name_;\n\tsystem(command.c_str());/g' src/modules/wlr/workspace_manager.cpp # use hyprctl to switch workspaces

    实现


启动终端并在终端内执行命令
`alacritty -t <title> -e <command>`
tui ftpscp工具


archlinux 开机自动启动
> https://blog.csdn.net/gddxz_zhouhao/article/details/52837593
https://wiki.archlinuxcn.org/wiki/Getty

添加：
/etc/systemd/system/getty@tty1.service.d/override.conf

```
[Service]
ExecStart=
ExecStart=-/usr/bin/agetty --autologin username --noclear %I $TERM
```


# 耗电测试

50min 13%
60@ 20%


# 鼠标不能用
https://bbs.archlinux.org/viewtopic.php?id=255844

https://wiki.archlinux.org/title/Power_management#USB_autosuspend
耗电模式不兼容



## talking head
1. 真正的nerf,借鉴动态nerf的方法,hyprnerf enerf dnerf
2. use 2d  generate method(vae)
3. 情绪
4. relighting


keyd 导致 鼠标不能用
https://bbs.archlinuxcn.org/viewtopic.php?id=13260











    22健康数据科学团支部

    22软件工程第一团支部

    22软件工程第二团支部




flash instead hop leap



github ssh 报错
https://blog.csdn.net/Horizon_carry/article/details/121874753
