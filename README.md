# rgnano_binary

Sponsorship is always welcome.
[https://ko-fi.com/trngaje](https://ko-fi.com/trngaje)

installer : FunKey Add on

You can download it from the following path.

[https://github.com/trngaje/rgnano_binary/releases/download/trngaje_230726/funkeyaddon_230728_4.opk](https://github.com/trngaje/rgnano_binary/releases/download/trngaje_230726/funkeyaddon_230728_4.opk)

Distribution is free, but please do not share files directly.
Only link shares that contain this description page are allowed.
It also does not allow sharing by repackaging individual files.

include advmenu, advmame, retroarch, runcommand

## new feature

### advmenu (frontend)

> 2x2 title

![](images/advmenu_2x2.png)


> runcommand

![](images/advmenu_runcommand.png)

> extra command in /mng/FunKey/.advance/advmenu.rc(this is not official)

    ui_runcommand_cfg /mnt/runcommand
    misc_languagefile hangulmenu.lng
    #ui_ip ifconfig wlan0 | grep 'inet addr' | cut -d: -f2 | awk '{print $1}' | tr -d '\n'
    #ui_battery cd /customer/app/ ; ./axp_test |  awk 'match($0, /"battery"/){print substr($0, 12, 3)}' | sed 's/,//'
    event_assign runcommand lshift
    event_assign cancel b

to display korean to english (comment below)
    /mng/FunKey/.advance/advmenu.rc

    #misc_languagefile hangulmenu.lng    

    ui_command_menu runcommand

>key assign

sel : display menu
Power : quit
A : select
start : flag for select item (ex. in emulator include)
B : cancel
l : page up
r : page down

### advmame

> autofire

![](images/advmenu_autofire.png)

> extra command in   /mng/FunKey/.advance/advmame.rc

to display korean to english (comment below)

    #misc_lang korea
    #misc_languagefile hangul.lng


>key assign

    L+R : display menu
    L+B : pause
    B : button 1
    A : button 2
    X : button 3
    Y : button 4
    Power : display exit menu

### simple terminal

support korean font to display

![](images/st_help.png)
![](images/st_keyboard.png)

to run a command script (need full path)
(hide welcome help with command script)

    st -e <command>

### retroarch

korean font : 11x11 instead of 10x10 official retroarch

![](images/retroarch11x11.png)
![](images/retroarch11x11_2.png)

I will also share the official version of 10x10 font.

### sdlretro

![](images/sdlretro_menu.png)
![](images/sdlretro_list.png)

    Applications
    	advmenu
    	st
    	retroarch

    Emulators
    	advmame

    bin
    	sdlretro
    	picoarch
    	retroarch
    		cores

    runcommand
    	runcommand.sh
    	cfg

    FunKey
    	.advance
    	.picoarch
    	.config
    	.sdlretro
    		cfg
    		saves
        system


rom path in advmenu.rc

    /mnt/mame-advmame/ (MAME 0.106 romsets)
    /mnt/mame2003/
    /mnt/mame2010/
    /mnt/fbneo/
    /mnt/Game Boy Advance/
    /mnt/NES/
    /mnt/SNES/
    /mnt/Game Boy/
    /mnt/Game Boy Color/
    /mnt/PCE-TurboGrafx/
    /mnt/megadrive/
    /mnt/msx/
    /mnt/pc/
    /mnt/pc98/
    /mnt/gameandwatch/

sub path

    snap/     - for snap images for rom (.png)
    mng/      - for mng,mp3 files for rom

prebuilt cores lists by myself

    mame2003_plus_libretro.so (korean menu)
    mame2010_libretro.so
    dosbox_pure_libretro.so
    snes9x_libretro.so
    gw_libretro.so
    fmsx_libretro.so
    bluemsx_libretro.so
    mgba_libretro.so
    np2kai_libretro.so


defined key value

basic keys

key value | function
--------- | --------
KEY_L | dpad left
KEY_R | dpad right
KEY_U | dpad up
KEY_D | dpad down
KEY_A | button A
KEY_B | button B
KEY_X | button X
KEY_Y | button Y
KEY_K | select
KEY_S | start
KEY_M | L
KEY_N | R
KEY_Q | quit


multi keys| key value
----------| --------
select + left | KEY_J
select + right | KEY_I
select + down | KEY_H
select + L | KEY_V
select + R | KEY_O
select+UP  |  nap
select+A   |  volume_up
select+Y   |  volume_down
select+X   |  bright_up
select+B   |  bright_down
select+L+R |  display_notif_system_stats


### license and reference

galmuri 11x11 font is included for advmame/advmenu

[https://github.com/quiple/galmuri/tree/main/dist](https://github.com/quiple/galmuri/tree/main/dist)

mng and mp3 files can be found for advmenu

[https://www.advancemame.it/download](https://www.advancemame.it/download)
