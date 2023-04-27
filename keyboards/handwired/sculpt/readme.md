# Microsoft Sculpt Wired Modification

Originally based on Michael Fincham's pinout [1] and keyboard definition [2], build a 
wired USB control board for the Microsoft Sculpt. 
KiCad files for board included.

This firmware finally based on Chaud Austin's pcb [3], keyboard and debouncer 
definitions [4]. Construction and early developing phases described on [5].

# Building firmware

This code has been written within QMK platform. Thus, it needs QMK to be set up 
on your machine.

## Make-style

Make example for this keyboard (after setting up your build environment):
```sh
make handwired/sculpt:default
```

## QMK-style
With QMK framework you can also compile the firmware using this command:
```sh
qmk compile -kb handwired/sculpt -km default
```
(!) With this approach, please ensure that working dir with sources is placed on:
```
# ~/qmk_firmware
```

# Flashing firmware

## Make-style
Flashing your firmware may be done with avrdude. The command should be something 
along this line:
```sh
avrdude -p usb1286 -c avr109 -P <COM PORT> -C <avrdude conf file> -e -u flash:w:handwired_sculpt_default.hex
```

## QMK-style
With QMK framefork you can flash firmware to your controller with a command 
like this:
```sh
qmk flash -kb handwired/sculpt -km default
```

The overall process is described [here](https://docs.qmk.fm/#/newbs_flashing) 

# Build environment set up

See the build environment setup [6] and the make instructions [7] for more 
information. Brand new to QMK? Start with our "Complete Newbs Guide" [8].




[1] https://github.com/fincham/wired-sculpt
[2] https://github.com/fincham/qmk_firmware_sculpt
[3] https://github.com/chadaustin/wired-sculpt-pcb
[4] https://github.com/chadaustin/qmk_firmware_sculpt
[5] https://chadaustin.me/2021/02/wiired-sculpt/
[6] https://docs.qmk.fm/#/getting_started_build_tools
[7] https://docs.qmk.fm/#/getting_started_make_guide
[8] https://docs.qmk.fm/#/newbs
