# Clean install of Windows (WIP)

## Prepare your USB stick:

1. Format the USB as NTFS, with GPT partition table
2. Name the NTFS volume "Winpe"
3. Copy the Windows 10 files from Chuwi to the Winpe volume.

## Set the tablet to Windows mode

1. In the BIOS change device mode to `Windows`

## Start the Windows installer
1. While booting, hold `F7` and select your USB stick
2. Windows PE will start and automatically try to erase the internal memory and install Windows.
 
If it fails to erase the internal memory, you can do it yourself with the following commands

```
diskpart
list disk
Select disk 0 (the emmc)
clean
convert gpt
exit
```

After that's done, reboot and select your USB stick again.

The installer will take a little while depending on the speed of your USB stick, and it will reboot the tablet a number of times during the install.
