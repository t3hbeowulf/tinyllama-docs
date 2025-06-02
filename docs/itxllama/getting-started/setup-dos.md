# Getting Started - Setting up DOS

The following guide will help you get started with setting up DOS on your ITX-Llama. 

---

### MS-DOS Installation

1. Choose your favorite VFD (Virtual Floppy Disc) in BIOS
1. Insert a blank SD card (128GB or less is ideal), or SATA SSD
1. Ensure you're booting from your chosen VFD by pressing `ESC` during start-up and selecting the Virtual Floppy image.
1. Format your chosen fixed storage device as normal. See example below: 
    * From the A: drive, run `fdisk c:` _follow the prompts._ 
      * Note: MS-DOS 6.22 is restricted to FAT16 out of the box and thus up to 4, 2GB partitions.
    * From the A: drive, run `format c: /s` _follow the prompts._
    * From the A: drive, run `copy *.* c:`
    * Adjust any file references in `autoexec.bat` / `config.sys`.
    * From the C: drive, run `fdisk /mbr` to ensure your C: drive is bootable.
    * Reboot.
1. As an alternative, the MiNiDOS VFD offers an install process which automates most of these steps.

---

### FreeDOS SD Card Image (pre-loaded)
1. Purchase an SD card from [Retrodreams.ca][Retrodreams-FreeDOS] preloaded with FreeDOS.
2. Check out this [README](freedos-sdcard.md)
3. Insert the SD Card into your ITX-Llama and enjoy!


### MS-DOS 6.22 Example Configs

``` batch title="config.sys"
DOS=HIGH,UMB
FILES=40
LASTDRIVE=Z
STACKS=9,256

DEVICE=C:\DOS\SETVER.EXE
DEVICE=C:\DOS\HIMEM.SYS /TESTMEM:OFF /VERBOSE
DEVICE=C:\DOS\SMARTDRV.EXE /DOUBLE_BUFFER
DEVICE=C:\DOS\EMM386.EXE RAM VERBOSE
```

``` batch title="autoexec.bat"
C:\WINDOWS\net start
C:\DOS\SMARTDRV.EXE /X
@ECHO OFF
PROMPT $p$g
PATH C:\WINDOWS;C:\DOS;C:\DRIVERS;C:\DRIVERS\MT32PI
SET TEMP=C:\DOS

LH C:\DRIVERS\CTMOUSE.EXE /r2

REM SoundCard Settings
set BLASTER=A220 I7 D1 H5 P330 J200
CWDMIX /M=15,15 /W=7,7 /L=15,15 /X=1 /F=15,15 /C=15,15 /I=C
```

Inspiration: [Fixing EMM386.exe with SMARTDRV and Double Buffering][msdos-doublebuffer]

---

### DOS Drivers
* [DOS Drivers](setup.md#dos-drivers)

---

### Windows 3.1 Tips

#### Video
For users with ATI Radeon 9XXX cards, be aware that no drivers were produced that are compatible with these cards natively from ATI. The Microsoft provided SVGA are also incompatible with this Radeon cards. In order to achieve 256 colors or higher, please consider the project utilizing the [vbesvga.drv][vbesvga] project.

#### Sound
After installing the Windows 3.1 drivers for the Crystal Audio, be sure to set the IRQ to 7 (the drivers default it to 5). Do this in the autoexec.bat, as well as the system.ini file.

---

[Back to Setup](setup.md) <br>
[Back to Getting Started](../getting-started.md)


[itxllama-repo]: https://github.com/eivindbohler/itxllama/archive/refs/heads/main.zip
[Retrodreams]: https://retrodreams.ca/collections/all
[Retrodreams-FreeDOS]: https://retrodreams.ca/products/preloaded-microsd-card-with-freedos-goodies
[winworldpc-win98]: https://winworldpc.com/download/417d71c2-ae18-c39a-11c3-a4e284a2c3a5
[vogons-thread]: https://www.vogons.org/viewtopic.php?t=93480
[vogons-minidos]: https://www.vogons.org/viewtopic.php?p=1307896#p1307896
[mt32-pi]: https://github.com/dwhinham/mt32-pi
[mt32-pi-control]: https://github.com/gmcn42/mt32-pi-control/tree/main/dos_bin
[vbesvga]: https://github.com/PluMGMK/vbesvga.drv
[msdos-doublebuffer]: https://info.wsisiz.edu.pl/~bse26236/batutil/help/SMARTD_S.HTM