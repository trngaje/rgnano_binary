### advmess

most of bios can be download on below site.

[link](https://ia802808.us.archive.org/view_archive.php?archive=/19/items/BIOS201808/BIOS.zip)

copy bios to run a machine to /mnt/advmess and run advmess


The supported bios can be found in the list below.

    advmess --listxml > output.xml

## 폴더 구조

    /usr/games/
    ├── advmame
    ├── advmenu
    ├── advmess

    /mnt/Anbernic or FunKey/
    ├── .advance
    │   ├── advmess.rc


## advmess.rc

setting the bios location (dir_rom is a bios location, not a game-rom)

    dir_rom /mnt/advmess


The game rom location is as follows. Unlike advmame, it is not important because advmess is not used as a frontend

    dir_image /mnt


The following settings are required for devices that do not display normally.

    device_video_clock 5 - 50 / 15.62 / 50 ; 5 - 50 / 15.73 / 60


The default key values for rgnano are as follows.
I have assigned a key to call configuration menu when both l and r keys are pressed.

    input_map[ui_configure] keyboard[0,m] keyboard[0,n]
    input_map[ui_up] keyboard[0,u]
    input_map[ui_down] keyboard[0,d]
    input_map[ui_left] keyboard[0,l]
    input_map[ui_right] keyboard[0,r]
    input_map[ui_select] keyboard[0,a]
    input_map[p1_up] keyboard[0,u]
    input_map[p1_down] keyboard[0,d]
    input_map[p1_left] keyboard[0,l]
    input_map[p1_right] keyboard[0,r]
    input_map[p1_button1] keyboard[0,a]
    input_map[p1_button2] keyboard[0,b]
    input_map[p1_button3] keyboard[0,x]
    input_map[p1_button4] keyboard[0,y]
    input_map[ui_cancel] keyboard[0,q]

You must assign a new key value for each game, and the assigned value is stored in advmess.rc (example)

    apple2ee[mnt_apple2_lode_runner_1983_broderbund]/input_map[p1_stick_left] keyboard[0,r]
    apple2ee[mnt_apple2_lode_runner_1983_broderbund]/input_map[p1_stick_right] keyboard[0,l]
    apple2ee[mnt_apple2_lode_runner_1983_broderbund]/input_map[p1_stick_up] keyboard[0,d]
    apple2ee[mnt_apple2_lode_runner_1983_broderbund]/input_map[p1_stick_down] keyboard[0,u]


## advmenu.rc settings

>Run directly with advmess

    emulator "nes" generic "advmess" "nes -cart %p"
    emulator_roms "nes" "/mnt/sdcard/roms/nes"
    emulator_roms_filter "nes" "*.nes"
    emulator_altss "nes" "/mnt/sdcard/roms/nes/mng:/mnt/sdcard/roms/nes/snap"

to run apple2 machine

    Confirmed bios : apple2e, apple2ee, apple2c, apple2gs

to run msx machine

machine that doesn't need bios

gen_jpn, gen_eur, gen_usa : Slow driving

pce, tg16  : possible to run

> Running with runcommand

wswan, wscolor

    emulator "wonderswan" generic "/mnt/runcommand/runcommand.sh" "wonderswan %p"
    emulator_roms "wonderswan" "/mnt/WonderSwan"
    emulator_roms_filter "wonderswan" "*.ws:*.wsc"
    emulator_altss "wonderswan" "/mnt/WonderSwan/mng:/mnt/WonderSwan/snap:/mnt/WonderSwan"


## runcommand settings


apple2.cfg

    DEFAULT="advmess apple2ee -flop"
    CORES[0]="advmess apple2ee -flop"
    CORES[1]="advmess apple2e -flop"
    CORES[2]="advmess apple2c -flop"
    CORES[3]="advmess apple2gs -flop"
    CORES[4]="advmess apple3 -flop"

msx.cfg

    CORES[7]="/mnt/bin/advmess msx -cart"

nes.cfg

    CORES[3]="advmess famicom -cart"

wonderswan.cfg

    CORES[2]="advmess wswan -cart"
    CORES[3]="advmess wscolor -cart"

megadrive.cfg

    CORES[5]="advmess gen_jpn -cart"
    CORES[6]="advmess gen_eur -cart"
    CORES[7]="advmess gen_usa -cart"


## video

for Miyoomini
[to disable malfunction keys for apple2e](https://youtu.be/o4ZhtZZNcV0?si=EAUzQNGa0ySM4YAu)
[loderunner playing](https://youtu.be/ac_l_zMCAEA?si=zU9qHflU_b9luJ3H)
