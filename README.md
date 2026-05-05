# Alpine on kindle (better)
Better Alpine for basically any kindle with more than 2GB of storage space

If you wanna lock your kindle, please don't lock it before you set these (if you dont wanna reboot your kindle)

`gsettings set org.mate.screensaver embedded-keyboard-enabled 'true' `

`gsettings set org.mate.screensaver embedded-keyboard-command 'onboard -e'`

Everything seems to works at it should, except some graphics bug in lock screen (more bugs, keep reading)
Expect 2-3 minutes delaying when clicking stuff in chromium while you are in a website lmao, remember to enable swap to use chromium

### !!WARNING!!

WHILE ALPINE IS RUNNING / THE IMAGE IS MOUNTED, DO NOT CONNECT YOUR KINDLE TO THE COMPUTER WITHOUT USBNETWORK ENABLED! The image resides in /mnt/us, and that is your usb mass storage location. When Alpine and the computer write on the userstore partition (partition 4) at the same time, it will be destroyed, and you need to fix that partition to get your Kindle working again. It might even be possible to brick the Kindle!!! Kual has an option to show the USBNetwork status, so check that beforehand if you plan on doing SSH while Alpine runs.

## Installation and launching 
- Put all the file in release to the /mnt/us, and open kterm, `cd /mnt/us` `sh alpine.sh` then `sh startgui.sh` if you need GUI (`startgui2.sh` is for testing on my pc though, for kindles its the startgui)
- ~~idk why launching in the kual didnt work but manual booting still works~~ use ``cp /mnt/us/alpine.conf /etc/upstart`` to use it from the launcher (i will make a script for it soon)

Notes: I forgot to fork it from schuhumi's repo but thanks for his `create_kindle_alpine_image.sh`

# Bugs
- When closing chromium, expect it to crash the UI and says killed in the term, so if you plan to use chromium then use drop to alpine
- Cant interact with Apperance background change

## Todo
- I will release a new version with fixed icons for you guys, maybe around march 15 if im free
