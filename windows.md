# Clean install of Windows (WIP)

Using the Windows 10 files provided by Chuwi here: http://forum.chuwi.com/thread-2116-1-1.html

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


# Updating to the Windows 10 Anniversary Update

If you're using the 32GB version of the Vi10 Plus, you won't have enough space to simply use Windows Update to install this, as it requires 20GB of free space.

If you make an installer USB stick using https://www.microsoft.com/en-gb/software-download/windows10 and upgrade from that, you can get around this limitation.

After you've upgraded everything, you can reclaim a further 5GB of space by doing a reset (Settings > Update & security > Reset this PC) and letting Windows go through the process of making itself immaculate. This will remove all of the Chuwi OEM branding and any other bits that came bundled in the Chuwi Windows 10 image, but all of the hardware works perfectly still.
