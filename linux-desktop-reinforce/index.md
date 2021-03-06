# Linux桌面环境美化


处理完的桌面环境看着比我还磕碜
<!--more-->

## 前言

[搭桌面环境后](/linux-desktop)

> 原因：丑，我不喜欢

找一下美化的资源～

下面这个还不错～

至少看起来是不错的～

目测用的是Gnome2、conky、gnome-terminal、docky、Faenza图标（我只要了Conky的配置「..「）

### 想要的效果

![网上搜来的](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/N22SLu.jpg "网上搜来的")

### 最终效果

![最终效果](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/HaV1pp.jpg "最终效果")

## 开始

### 护眼桌面

先来定张桌面背景～贯彻保护眼睛的方针～

![护眼背景](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/473Ftg.jpg "护眼背景")

### Slim（Display Manager）

先安装主题包`# pacman -S slim-themes archlinux-themes-slim`

然后`#vim /etc/slim.conf`，将current_theme修改成想要的主题

我用的是这个`archlinux-darch-white`

![Archlinux登陆](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/lHxeEE.jpg "Archlinux登陆")

### 窗口管理器Openbox

使用 openbox 窗口主题，我用Owl，直接下载下来用 obconf 安装就OK啦

![openbox](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/Mp1ZXj.jpg "Openbox")

除了Openbox的主题，还需要配置软件的主题Gtk2、Gtk3、Qt的主题都用clearlook，字体就用文泉译的

配置Gtk2和Qt主题，先安装`gtk-chtheme qtcurve-qt4`

然后运行`gtk-chtheme`（必要的gtk引擎需要安装），

![gtk-chtheme](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/OiwDX5.jpg "gtk-chtheme")

运行 `qtconfig-qt4`，GUI Style 选择 GTK+，尽量让 Qt 和 Gtk2 主题一致

![qtconfig-qt4](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/7NEaDe.jpg "qtconfig-qt4")

剩下个Gtk3（本来不想弄的，偏偏有个gedit是GTK3的..），从AUR中安装`clearlooks-phenix-gtk-theme`，然后编辑`$HOME/.config/gtk-3.0/Settings.ini`文件，没有就创建，将`gtk-theme-name = Clearlooks-Phenix`添加到[Settings]下

### 图标

～～ 最主要的是文件管理器的图标（表示刚装完pcmanfm的时候毛都没有），同样是桌面的图标（我使用conky，没用pcmanfm上的桌面），还有taskbar显示的图表，最后是快捷启动栏的图标，首先是下载安装各种图标，AUR上大把，图标一般在 `/usr/share/icons/` 文件夹下，对应的文件夹名就是图标主题名，或者闲得蛋疼自己下载的，应放在`$HOME/.icons/`文件夹下

默认的.gtkrc-2.0会改变，但是里面有个include包含了文件.gtkrc-mine，所以，`touch .gtkrc-mine && echo gtk-icon-theme-name = "icon_theme" >> .gtkrc.mine`

基本上软件的界面什么的就这么OK了（应该吧「_「///）

### 配置tint2

接下来是配置tint2～

下面介个是我的配置文件～简单为主～

```
# Tint2 config file
# Generated by tintwizard (http://code.google.com/p/tintwizard/)
# For information on manually configuring tint2 see http://code.google.com/p/tint2/wiki/Configure

# To use this as default tint2 config: save as $HOME/.config/tint2/tint2rc

# Background definitions
# ID 1 panel
rounded = 0
border_width = 0
background_color = #222222 100
border_color = #000000 100

# ID 2 taskbar
rounded = 0
border_width = 0
background_color = #000000 100
border_color = #224466 100

# ID 3 task
rounded = 0
border_width = 0
background_color = #FFA300 100
border_color = #224488 100

# Panel
panel_items = LTSC
panel_monitor = all
panel_position = bottom left horizontal
panel_size = 100% 22
panel_margin = 0 0
panel_padding = 0 0 0
panel_dock = 0
wm_menu = 1
panel_layer = bottom
panel_background_id = 1

# Launchers
launcher_icon_theme = AwOkenDark
launcher_padding = 5 0 5
launcher_background_id = 0
launcher_icon_size = 22
launcher_item_app = /home/XXOO/.config/tint2/applications/shutdown.desktop
launcher_item_app = /usr/share/applications/chromium.desktop
launcher_item_app = /usr/share/applications/gimp.desktop
launcher_item_app = /usr/share/applications/gedit.desktop
launcher_item_app = /usr/share/applications/pcmanfm.desktop
launcher_item_app = /usr/share/applications/goldendict.desktop

# Panel Autohide
autohide = 0
autohide_show_timeout = 0.3
autohide_hide_timeout = 2
autohide_height = 2
strut_policy = follow_size

# Taskbar
taskbar_mode = single_desktop
taskbar_padding = 0 0 5
taskbar_background_id = 0
#taskbar_active_background_id = 2

# Tasks
urgent_nb_of_blink = 8
task_icon = 1
task_text = 1
task_centered = 1
task_maximum_size = 180 20
task_padding = 5 5
task_background_id = 0
task_active_background_id = 3
task_urgent_background_id = 0
task_iconified_background_id = 0

# Task Icons
task_icon_asb = 100 0 0
task_active_icon_asb = 100 0 0
task_urgent_icon_asb = 100 0 0
task_iconified_icon_asb = 100 0 0

# Fonts
task_font = sans 8
task_font_color = #999999 80
task_active_font_color = #343434 100
task_urgent_font_color = #FFFFFF 100
task_iconified_font_color = #FFFFFF 80
font_shadow = 0

# System Tray
systray = 1
systray_padding = 5 0 5
systray_sort = ascending
systray_background_id = 0
systray_icon_size = 22
systray_icon_asb = 100 0 0

# Clock
time1_format = %H:%M %A %d
time1_font = sans 8
clock_font_color = #00FF00 100
clock_padding = 10 0
clock_background_id = 0
clock_rclick_command = orage

# Tooltips
tooltip = 0
tooltip_padding = 5 5
tooltip_show_timeout = 0.3
tooltip_hide_timeout = 0.3
tooltip_background_id = 6
tooltip_font = sans 10
tooltip_font_color = #000000 100

# Mouse
mouse_middle = none
mouse_right = none
mouse_scroll_up = none
mouse_scroll_down = none

# Battery
battery = 0
battery_low_status = 10
battery_low_cmd = notify-send "battery low"
battery_hide = 100
bat1_font = sans 8
bat2_font = sans 6
battery_font_color = #8CA587 73
battery_padding = 0 0
battery_background_id = 1

# End of config
```

### 自定义关机按钮

`launcher_item_app = /home/{user}/.config/tint2/applications/shutdown.desktop`，直接关机的按钮（没写复杂脚本，直接点击就是`poweroff`），Icon是在图标主题里找的

```
[Desktop Entry]
Name=Poweroff
Comment=poweroff
Exec=/usr/bin/poweroff
Icon=/usr/share/icons/AwOken/clear/24x24/apps/gshutdown.png
Terminal=false
Type=Application
Categories=Application;
```

Conky用的是第一张图片的那个，叫Infinity，然后自己修改conkyrc，添加了个RSS

BTW：透明化可以用transset-df，阴影可以用xcompmgr，我效果里用了一点点阴影

### 最后再看一看

![我简直是天才](https://gitee.com/toddlam/Colony/raw/master/pic/2020-05-08/HaV1pp.jpg "我简直是天才")
