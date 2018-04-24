Pseudo-Brightness-Driver
====

A linux kernel module to control brightness using keyboard.
This is an experiment to fiddle with drivers. It may not have any real life use case but was fun to create.
It still has some bugs and needs a lot of improvements.

### To run

+ Use `make` to generate .ko file
+ Install using `insmod bright.ko files`
+ Go to `cd /dev` and create `sudo mknod /dev/bright c 242 0` where 242 will be replaced by major number given while installing this module. This major number can be viewed in logs using `dmesg`
+ Provide permission to this char file `sudo chmod 777 bright`
+ To remove `rmmod bright`
+ To view available kernel mods `lsmod`

### To provide input from keyboard

Use the available commands:
All of the commands are being fed into dev mousek char file. This can be done by echo in `/dev` directory.
For example -
```sh
$ echo "b" > /dev/bright
$ echo "v" > /dev/bright
```
+ "b" is to increase brightness
+ "v" is to decrease brightness

Aslo there is a shell scipt run it as that reads in input from user infinitely:
```./b.sh```

### Team Members
* [Nishant Kumar](https://github.com/NishantKr97),16IT123
* [Dhvanil Parikh](https://github.com/DhvanilP), 16IT217
* [Suyash Ghuge](https://github.com/suyash0103), 16IT114
* [Shreyas Shankar](https://github.com/shrey920), 16IT138

### License
This kernel module comes with a MIT license.
