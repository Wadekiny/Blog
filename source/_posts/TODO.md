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
