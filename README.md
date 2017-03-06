自己开个中文翻译,方便之后研究方便FORKED REPO NOTES:
==================

通过给主板 teensy 2.0 (基于Smasher816) 编程,制作可自定义的USB键盘转换器: http://geekhack.org/index.php?topic=57008.0

Note that this fork isn't current with tmk (I'm not rebasing this and if I do so I'll probably move this to a new repository) as recent commits broke my builds (even clean builds with no customization) so I'm keeping this here as a historical snapshot of working teensy 2.0 固件.

Most of my customizations are in the keyboard/hhkb subdirectory. See the changes I made in the following commit: https://github.com/altercation/tmk_firrmware_hhkb_teensy2/commit/b1725e96a633bdb5ff54d397260b66210cbedead

TMK 键盘固件
================================
这是一个为Atmel AVR控制器提供的的功能键盘固件。

源代码在这里: <http://github.com/tmk/tmk_keyboard>


特性
--------
这些功能可用于您的键盘.

* Multi-layer Keymap  - 具有层切换的多个键盘布局
* Mouse key           - 可以通过键盘模拟鼠标
* System Control Key  - 关机，休眠，唤醒，USB远程唤醒
* Media Control Key   - Volume Down/Up, Mute, Next/Prev track, Play, Stop and etc
* USB NKRO            - 120 键(+ 8 转换键)
* PS/2 mouse support  - PS/2 鼠标(小红点) 符合键盘
* Keyboard protocols  - PS/2, ADB, M0110, Sun and other old keyboard protocols
* User Function       - 具有可编写代码的键位的可定制功能
* Macro               - 宏定义,(目前还很原始)
* Keyboard Tricks     - Oneshot modifier and modifier with tapping feature
* Debug Console       - 调试和与固件交互的消息
* Virtual DIP Switch  - 配置存储EEPROM（魔术引导）
* Locking CapsLock    - 为支持大写锁机械开关
* Breathing Sleep LED - 睡眠呼吸led灯
* Backlight           - 控制背光功能


项目
--------
你可以在下面目录`converter` 和 `keyboard` 中找到一些键盘特定的项目 .

### converter 转换器
* [ps2_usb](converter/ps2_usb/)             - [PS/2 keyboard to USB][GH_ps2]
* [adb_usb](converter/adb_usb/)             - [ADB keyboard to USB][GH_adb]
* [m0110_usb](converter/m0110_usb)          - [Macintosh 128K/512K/Plus keyboard to USB][GH_m0110]
* [terminal_usb](converter/terminal_usb/)   - [IBM Model M terminal keyboard(PS/2 scancode set3) to USB][GH_terminal]
* [news_usb](converter/news_usb/)           - [Sony NEWS keyboard to USB][GH_news]
* [x68k_usb](converter/x68k_usb/)           - [Sharp X68000 keyboard to USB][GH_x68k]
* [sun_usb](converter/sun_usb/)             - [Sun] to USB(type4, 5 and 3?)
* [pc98_usb](converter/pc98_usb/)           - [PC98] to USB
* [usb_usb](converter/usb_usb/)             - USB to USB(experimental)
* [ascii_usb](converter/ascii_usb/)         - ASCII(Serial console terminal) to USB
* [ibm4704_usb](converter/ibm4704_usb)      - [IBM 4704 keyboard Converter][GH_ibm4704]

### keyboard 键盘
* [hhkb](keyboard/hhkb/)                    - [Happy Hacking Keyboard pro][GH_hhkb] **我的主力键盘 (翻译者也是)**
* [gh60](keyboard/gh60/)                    - [GH60] DIY 60% keyboard [prototype][GH60_proto] **my second board**
* [hbkb](keyboard/hbkb/)                    - [Happy Buckling spring keyboard][GH_hbkb](IBM Model M 60% mod)
* [hid_liber](keyboard/hid_liber/)          - [HID liberation][HID_liber] controller (by alaricljs)
* [phantom](keyboard/phantom/)              - [Phantom] keyboard (by Tranquilite)
* [IIgs_Standard](keyboard/IIgs/)           - Apple [IIGS] keyboard mod(by JeffreySung)
* [macway](keyboard/macway/)                - [Compact keyboard mod][GH_macway] [retired]
* [KMAC](keyboard/kmac/)                    - Korean custom keyboard
* [Lightsaber](keyboard/lightsaber/)        - Korean custom keyboard

[GH_macway]:    http://geekhack.org/showwiki.php?title=Island:11930
[GH_hhkb]:      http://geekhack.org/showwiki.php?title=Island:12047
[GH_ps2]:       http://geekhack.org/showwiki.php?title=Island:14618
[GH_adb]:       http://geekhack.org/showwiki.php?title=Island:14290
[GH_hhkb_bt]:   http://geekhack.org/showwiki.php?title=Island:20851
[GH_m0110]:     http://geekhack.org/showwiki.php?title=Island:24965
[GH_news]:      http://geekhack.org/showwiki.php?title=Island:25759
[GH_terminal]:  http://geekhack.org/showwiki.php?title=Island:27272
[GH_x68k]:      http://geekhack.org/showwiki.php?title=Island:29060
[GH_hbkb]:      http://geekhack.org/showwiki.php?title=Island:29483
[GH_ibm4704]:   http://geekhack.org/index.php?topic=54706.0
[HID_liber]:    http://deskthority.net/wiki/HID_Liberation_Device_-_DIY_Instructions
[Phantom]:      http://geekhack.org/index.php?topic=26742
[GH60]:         http://geekhack.org/index.php?topic=34959
[GH60_proto]:   http://geekhack.org/index.php?topic=37570.0
[PC98]:         http://en.wikipedia.org/wiki/NEC_PC-9801
[Sun]:          http://en.wikipedia.org/wiki/Sun-3
[IIGS]:         http://en.wikipedia.org/wiki/Apple_IIGS



License 许可证(你都懂了,反正自己把键盘给作坏了别来找我)
-------
**GPLv2** or later. Some protocol files are under **Modified BSD License**.
LUFA, PJRC and V-USB stack have their own license respectively.



如何编译烧写固件
-------------------------------------
看这个文件 [doc/build.md](doc/build.md).



修改你的键位映射(我主要就像要这个功能)
------------------
See [doc/keymap.md](doc/keymap.md).



魔术命令
--------------
按 `Magic` + `H`查看帮助.

 `Magic` key bind may be `LShift` + `RShift` in many project, but `Power` key on ADB converter. `Magic` keybind can be vary on each project, check `config.h` in project directory.

Following commands can be also executed with `Magic` + key. In console mode `Magic` keybind is not needed.

    ----- Command Help -----
    c:      进入命令行模式console model
    d:      开关debug
    x:      开关矩阵debug
    k:      开关键盘debug
    m:      开关鼠标debug
    v:      输出版本号
    t:      输出时间记录
    s:      输出状态status
    e:	    输出eeprom配置
    n:	    toggle NKRO
    0/F10:  switch to Layer0
    1/F1:   switch to Layer1
    2/F2:   switch to Layer2
    3/F3:   switch to Layer3
    4/F4:   switch to Layer4
    PScr:   power down/remote wake-up
    Caps:   Lock Keyboard(Child Proof)
    Paus:   jump to bootloader

**TBD**

### Boot Magic Configuration - Virtual DIP Switch
Boot Magic are executed during boot up time. Press Magic key below then plug in keyboard cable.
Note that you must use keys of **Layer 0** as Magic keys. These settings are stored in EEPROM so that retain your configure over power cycles.

To avoid configuring accidentally additive salt key `KC_SPACE` also needs to be pressed along with the following configuration keys. The salt key is configurable in `config.h`. See [common/bootmagic.h](common/bootmagic.h).

#### General
- Skip reading EEPROM to start with default configuration(`ESC`)
- Clear configuration stored in EEPROM to reset configuration(`Backspace`)

#### Bootloader
- Kick up Bootloader(`B`)

#### Debug
- Debug enable(`D`)
- Debug matrix enable(`D`+`X`)
- Debug keyboard enable(`D`+`K`)
- Debug mouse enable(`D`+`M`)

#### Keymap
- Swap Control and CapsLock(`Left Control`)
- Change CapsLock to Control(`Caps Lock`)
- Swap LeftAlt and Gui(`Left Alt`)
- Swap RightAlt and Gui(`Right Alt`)
- Disable Gui(`Left Gui`)
- Swap Grave and Escape(`Grave`)
- Swap BackSlash and BackSpace(`Back Slash`)
- Enable NKRO on boot(`N`)

#### 默认层
- Set Default Layer to 0(`0`)
- Set Default Layer to 1(`1`)
- Set Default Layer to 2(`2`)
- Set Default Layer to 3(`3`)
- Set Default Layer to 4(`4`)
- Set Default Layer to 5(`5`)
- Set Default Layer to 6(`6`)
- Set Default Layer to 7(`7`)

#### 注意!
使用此功能会导致用户混淆。

TODO: Magic key combination to avoid unintentional press during plug in

**TBD**


机械锁支持
--------------------------
这个功能可以让您使用机械开关`CapsLock`, `NumLock` or `ScrollLock`。启用该功能`config.h` 和使用`KC_LCAP`, `KC_LNUM` or `KC_LSCR`在映射关键而不是正常的 `KC_CAPS`, `KC_NLCK` or `KC_SLCK`。同步选项尝试保持锁开关状态一致的LED键盘状态。
 
    #define LOCKING_SUPPORT_ENABLE
    #define LOCKING_RESYNC_ENABLE


开始建立你自己的项目
-----------------------
**TBD**
### Config.h 选项
#### 1. USB vendor/product ID and device description
    #define VENDOR_ID       0xFEED
    #define PRODUCT_ID      0xBEEF
    #define MANUFACTURER    t.m.k.
    #define PRODUCT         Macway mod
    #define DESCRIPTION     t.m.k. keyboard firmware for Macway mod

#### 2. Keyboard matrix configuration
    #define MATRIX_ROWS 8
    #define MATRIX_COLS 8
    #define MATRIX_HAS_GHOST



项目图解
------------
    架构图
                               +---------------+---------------+-------------+
                               |    Host       |   Keyboard    | Matrix, LED |
       ___________             |-----------+-+ +-------------+ | +-----------|
      /          /| Keys/Mouse | Protocol  |d| | Action      | | | Protocol  |
     /__________/ |<-----------|  LUFA     |r| |  Layer, Tap | | |  Matrix   |
     |.--------.| |   LED      |  V-USB    |i| |-------------| | |  PS/2,IBM |             __________________
     ||        || |----------->|  PJRC     |v| | Keymap      | | |  ADB,M0110|  Keys      / /_/_/_/_/_/_/_/ /|
     ||  Host  || |  Console   |  iWRAP(BT)|e| | Mousekey    | | |  SUN/NEWS |<----------/ /_/_/_/_/_/_/_/ / /
     ||________||/.<-----------|  UART     |r| | Report      | | |  X68K/PC98| Control  / /_/_/_/_/_/_/_/ / /
     `_========_'/|            |---------------------------------------------|-------->/___ /_______/ ___/ /
     |_o______o_|/             | Sendchar, Print, Debug, Command, ...        |         |_________________|/
                               +---------------------------------------------+              Keyboard



调试
--------
使用 PJRC 的 `hid_listen` 来查看调试信息. 你可以使用的工具，即使使用该LUFA堆栈调试固件.

你可以使用 xprintf() 显示调试信息 `hid_listen`, 查看文件 `common/xprintf.h`.



项目文件和目录
-------------------
### Top
* common/       - 常用代码
* protocol/     - 键盘协议支持
* keyboard/     - 键盘项目
* converter/    - 协议转换器项目
* doc/          - 文档
* common.mk     - Makefile for common
* protocol.mk   - Makefile for protocol
* rules.mk      - Makefile for build rules

### Common
* host.h
* host_driver.h
* keyboard.h
* command.h
* keymap.h
* action.h
* keycode.h
* matrix.h
* led.h
* mousekey.h
* report.h
* debug.h
* print.h
* bootloader.h
* sendchar.h
* timer.h
* util.h

### 键盘协议
* lufa/     - LUFA USB stack
* pjrc/     - PJRC USB stack
* vusb/     - Objective Development V-USB
* iwrap/    - Bluetooth HID for Bluegiga iWRAP
* ps2.c     - PS/2 protocol
* adb.c     - Apple Desktop Bus protocol
* m0110.c   - Macintosh 128K/512K/Plus keyboard protocol
* news.c    - Sony NEWS keyboard protocol
* x68k.c    - Sharp X68000 keyboard protocol
* serial_soft.c - Asynchronous Serial protocol implemented by software



代码风格
-------------
- 4个空格代替tab.



其余项目
------------------
See [doc/other_projects.md](doc/other_projects.md).




