# Clean install of Windows (WIP)

use rufus to make gpt ntfs usb stick, volume name WINPE
copy win10 files

bios, change mode from android to windows

boot, select windows

it will fail if you've still got a linux/android formatted emmc


the following will erase emmc so windows can be installed

```
diskpart
list disk
Select disk 0 (the emmc)
clean
convert gpt
exit
```

reboot, select windows again

it will install successfully, will take a while

reboot, remove usb, select windows

it will take a little while and will reboot a couple of times

you will be prompted through the getting started process
