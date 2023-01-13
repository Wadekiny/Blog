---
title: TODO
mathjax: true
tags: [todo]
date: 9000-01-01 22:50:05
categories: todo
description: todo list
---



目的：
恢复更仿真的人脸：

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


pyright opencv
clash for windows git加速(还是用qv2ray把)
舞蹈和人脸合成一起

纹理细节为什么不好？


无线电 群里的论文
expgan


i3: autotiling
i3: lxappearance

vim: vim-surround (ysiw3*)
vim: startify
vim: lightline, bufferline
vim: coc-explorer
vim: plugin - treesitter- too long 'if,for,class,function...,' 
vim: line tab4 highlight
vim: highlight func class...too long 
vim: pwd at right top
vim: set autochdir 自动改变工作目录
：cd改变工作目录
see more details: `:h expand`

.zshrc
alias todo='nvim ~/BLOG/source/_posts/TODO.md'

coc补全边框圆角显示问题巴拉巴拉，是alacritty的问题，更新最新版的alacritty，就好了

system: asd2123
ranger:select-editor







sogou
nvidia驱动








dwm,i3获取窗口 
xprop
xwininfo
notify-osd
dunst!
dunst要不要加到开机启动？
vim:hex 16进制表示方法
:set laststatus=2
`:set statusline=%<%f%h%m%r%=%b\ 0x%B\ \ %l,%c%V\ %P`

dwm statusbar 日期部分显示异常，加正则表达式替换
 cal | sed  's/_/test/g' | nvim
：
cal | sed 's/_^H/ /' | sed 's/  _^H/>/'
正则替换每一个可能的清空
dwm statusbar路径设置
vim 正则表达式替换
vim宏+1功能 c-a
ls20东蒙人工智能团支部p
clash for window
wsl代理需要设置防火墙
ip到底是哪个？

easyconnect 打开导致不能git push


proxy打开后，pip install报错 https://blog.csdn.net/tuzixini/article/details/88203910
mason 不能安装python-lanuage-server https://www.saoniuhuo.com/question/detail-2133503.htmlcli

2022-12-23T16:57:49 Warning  WARN Client 1 quit with exit code 1 and signal 0 ,checkhealth,是不是有依赖不匹配


1. kitty and Chinese
2. Xauthority should be wadekiny's, instaed, login loop
3. Nvidia driver should be 470.xxx. or black screen
4. a lot of nvim stateline
5. i3-gaps
6. fcitx
7. ranger kitty preview image
8. i3 picom ,is updating
9. betterlockscreen  need i3lock ..
10. git speed up
11. press mod+p to imput password
12. filename from window will be wired
13. kitty do not support chinese input method, rustup ,cargo and alacritty
14. ranger default text editor
15. 删除团员
16. pynput need sudo apt install python3-tk python3-dev
17. pyautogui 可以弹窗

import pyautogui

# 显示一个简单的带文字和OK按钮的消息弹窗。用户点击后返回button的文字。
pyautogui.alert(text='', title='', button='OK')


~/.fonts/ 添加字体文件，可以直接安装字体
dunst是系统自带的
/usr/share/xsession/dwm.desktop
lsp
dwm-statusbar有时候不显示，是因为temp里多了一对@,不知道为什么
windows的zip文件在ubuntu解压乱码k


 install arch linux
 merge code new roman and maiyuan
  fcixt5 vim 
 sound pulseaudio dwm shortcut change volume use pactl instead of axmier

 how to view a key code? like
    { 0,    XF86XK_AudioLowerVolume,  spawn, SHCMD("pactl set-sink-volume @DEFAULT_SINK@ -5%") },                              /* super shift down | 音量减                 */
    xkxxxxxxx

#include <X11/XF86keysym.h>?


 amd-display-xf?? 装了后显示异常，不如不装
 pip 换源

 网卡驱动
 realtek rtl8852be wifi 6 802.11ax pcie adapter  archlinux 驱动

 开机不自动换esc capslock？
 
grub add windows

feh dnust betterlockscreen rofi picom dwm 

.Xresources 
.xinitrc
免密自动登录 startx

clash for windows

aur makepkg
nm-applet 貌似是ubuntu下的，arch不能用 ,用nm-tray-git





esc2caps 和 fcitx5 -d 都放到autostart里不行

fcitx5 -d 不在autostart时，esc2caps起作用
起作用后在启动fcitx5 -d esc2caps 又不起作用了
再esc2caps,又起作用了

所以是fcitx5重置了esc2caps
https://wiki.archlinux.org/title/fcitx
提到了 fcitx会覆盖xmodmap的作用
Fcitx now control keyboard layout and when switch layout, xmodmap setting will be overwritten. So fcitx-xkb provides an option to specify the xmodmap script and let fcitx loads it for you whenever keyboard layout changes. Or disable fcitx-xkb addon is also a solution for you, or if your requirement is simply, for example, switching Caps Lock and Esc, which is provided by xkb option, you can just set it with your desktop keyboard configuration tool (Gnome and KDE all support such configuration).

For more detailed explanation, xmodmap is a very low level tool, that doesn't aware keyboard layout. For X11, keyboard layout is built on a set of profile, when such profile is loaded, anything you changed with xmodmap will be overwritten, this isn't specific to fcitx, but all tool that support keyboard layout configuration. Xkb option is a set of profile that can do some pre-defined change over keyboard layout, including many thing that people usually do with xmodmap, for example, defining where dead key is, switching Caps Lock and Esc, and so on. Unless you have special requirements, xkb layout and xkb option is recommended.

Since 4.2.7, Fcitx will try to load ~/.Xmodmap if it exists.

由于不只是fcitx会出现此情况，其他软件也有可能，解决方法最好是用xkb(Xorg/Keyboard configuration)

setxkbmap -option "caps:swapescape"




neovide can implement cursors smooth but can not input Chinese
how to set fonts?????????


maiyuan font : 11904 start  end 184000 ,放弃了 并且使用jetbrains nerdfont字体，其他字体可能不会对齐

neovide不能输入中文，winit？


zotero


aur:
yay:
sudo pacman -S yay
坚果云 zotero

安装微信需要打开multilib
https://blog.csdn.net/weixin_52027058/article/details/128346840


fontforge合并字体之后 还要在小修改一下符号，避免边框对不起(然而含麻烦)


微信https://github.com/vufa/deepin-wine-wechat-arch#%E4%BB%8Eaur%E5%AE%89%E8%A3%85


https://github.com/vufa/deepin-wine-wechat-arch#%E4%BB%8Eaur%E5%AE%89%E8%A3%85
ohttps://www.bilibili.com/video/BV1Z3411F7TL/?spm_id_from=333.337.search-card.all.click&vd_source=c59669dc10d72873dc1a840e4c9b6095





flameshot 截图不能直接复制到qq 微信 no tray refer:
https://wiki.archlinux.org/title/Flameshot

vim 如何在浮动窗口和普通窗口切换
023-01-12T19:23:37 Messages  INFO line    8:
Needs xclip in X11 or wl-clipboard in Wayland.
2023-01-12T19:23:37 Error  ERROR Error detected while processing function MdPasteImage[5]..mdip#MarkdownClipboardImage[23]..<SNR>58_SaveFileTMP[6]..<SNR>58_SaveFileTMPLinux:
2023-01-12T19:23:49 Messages  INFO 2023-01-12T19:23:37 Messages  INFO line    8:
Needs xclip in X11 or wl-clipboard in Wayland.
2023-01-12T19:23:37 Error  ERROR Error detected while processing function MdPasteImage[5]..mdip#MarkdownClipboardImage[23]..<SNR>58_SaveFileTMP[6]..<SNR>58_SaveFileTMPLinux:
2023-01-12T19:24:01 Error  ERROR E488: Trailing characters: list


flameshot &
flameshot gui
https://github.com/flameshot-org/flameshot/issues/2496



xorg 缩放倍数
设置鼠标样式 大小
https://wiki.archlinuxcn.org/zh-hans/%E5%85%89%E6%A0%87%E4%B8%BB%E9%A2%98
lxapperance

文件夹可视化管理
nautilus

xrandr --output e-DP1 --scale 0.5x0.5

npm fanyi 的问题
https://github.com/afc163/fanyi#error-spawn-festival-enoent
sudo apt-get install festival festvox-kallpc16k

arch无法识别typec接口显示器


设置亮度 sudo echo 50 > /sys/class/backligh^Cmdgpu_bl0/brightness
root用户才行，sudo不能获取root全部权限


获取窗口名称？

挂载windows分区https://zhuanlan.zhihu.com/p/513859236


怎么有时候会卡死？好像和fcitx有关
grub不能识别windows
从archlinux.md中拆分 profile bashrcxxxxx优先级，形成一篇新的

Xresources修改dpi？
https://zhuanlan.zhihu.com/p/513859236
wechat 锁更新
okular pdf查看器查看器
