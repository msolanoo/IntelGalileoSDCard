IntelGalileoSDCard
==================

Best Known Working method to boot Intel Galileo from SD Card

If you wish to keep your programs in your Galileo card, so that you can run them again even though you unplug your power supply...you must boot from an SD card.  Also, this is required to enable Wifi.
It took me almost a full afternoon to make it work, actually is not difficult, but there are some tricks.

Preparation:
- Get an SD card!
- YOU MUST update the Galileo firmware.  In order to do this, connect your Galileo Card to your computer and start the Arduino IDE software.  Go to "Help" Menu and click on "Firmware Update".
- Get the SD card Linux Image from http://downloadmirror.intel.com/23171/eng/LINUX_IMAGE_FOR_SD_Intel_Galileo_v0.7.5.7z

Procedure:
- Unzip the files to a folder in your hard drive
- YOU MUST format your SD Card and clean all file, to do this: Insert the microSD card into your computer.
- Open a cmd.exe as Administrator. 
- Run diskpart.exe,
- Then these commands: 
     select vol e (whatever drive letter the stick is); 
     clean ;
     create part primary;
     active ;
     format quick label="BOOTME";
     exit
- Navigate into the folder where you unzip the SD card image, which will be called LINUX_IMAGE_FOR_SD_Intel_Galileo_v0.7.5 (or similar).
- Select all the files, right-click and click Copy.
- Windows will ask what you’d like to do. Select “Open folder to view files.”
- Right-click in the drive window and click Paste to copy the files from the folder you extracted. When you browse the files on your card, you should have a boot folder and three other files.

You will know that it's booting from your SD card because you'll see the green SD LED blink and flash for about 40-60 seconds after applying power.  Then the blinking will stop.
