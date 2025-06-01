# Getting Started - Setting Up Your ITX-Llama

The following set of guides aim to help you set up an operating system on your ITX-Llama. 

---

### MS-DOS Installation

See [MS-DOS Setup Guide](setup-dos.md)

---

### Windows 98 Installation

See [Windows 98 Setup Guide](setup-win98.md)

---

### FreeDOS SD Card Image (pre-loaded)
1. Purchase an SD card from [Retrodreams.ca][Retrodreams-FreeDOS] preloaded with FreeDOS.
2. Check out this [README](freedos-sdcard.md)
3. Insert the SD Card into your ITX-Llama and enjoy!

---

### DOS Drivers

* [ctmouse.exe][driver-CTMOUSE] - The venerable FreeDOS Mouse Driver - CTMouse! (v2.1b)
* [pmouse.com][driver-PMOUSE] - A smaller, lighter sometimes more compatible alternative to CTMouse
* [r6040dos.zip][driver-r6040dos] - (Optional) an R6040 Ethernet NDIS driver for DOS and Windows 3.1.

### Windows 98 Drivers

* [Crystal 4237b v2.86][driver-win98-CWD] - Windows 98 drivers tuned for the Llama's Crystal 4237b sound chip.
* [Realtek R6040 10/100 NIC][driver-win98-R6040] - Windows 98 drivers for the integrated Vortex86EX network interface.
* [Large Drive Support (tbplus) Patch][driver-win98-TBPLUS] - Windows 98 Patch for Large HDD support. (subset of TBPlus Pack)
* [USB Removable Storage Driver][driver-win98-USB] - Windows 98 USB removable storage driver (nusb36e)
* [Alternative Crystal Drivers][driver-crystal-archive] - Archive of alternative Crystal Sound Drivers 

---

### Crystal Audio Setup

For DOS / Windows 3.1 / Windows 98, in order to properly configure sound (including mt32-pi/dreamblaster/OPL-3), ensure the following lines are in your `autoexec.bat`: _(This applies to Windows 98 as well)_

```
SET BLASTER=A220 I7 D1 T5 P330 J201
C:\CRYSTAL\CWDMIX /M=13,13 /W=13,13 /L=13,13 /X=1 /F=13,13 /C=13,13 /I=L
```

On Windows 98, install the [Crystal 4237b v2.86][driver-win98-CWD] audio drivers onto your system. 

This should resolve any audio issues, including optical out problems. Be aware the dreamblaster and mt32-pi are configured to come in as "line-in", so use that slider to adjust their volumes.

---

### Boot Managers
While there are many boot managers that are available to use, in some configurations (specifically booting from SSD first, then MicroSD), please consider using the boot manager that is included with `xfdisk.exe` as part of the Windows 98 Setup VFD included with the BIOS. The author of this section had tested about 6 different boot managers, and this was the only one that was able to work correctly.

---

### Tools

* [cwdmix.exe][tool-CWDMIX] - DOS Utility for setting mixer levels for the Crystal 4237b sound chip.
* [anybios.exe][tool-ANYBIOS] - DOS Utility for flashing the ITX Llama system BIOS.
* [slowdown.zip][tool-SLOWDOWN] - DOS Utility for slowing the CPU down even further than the lowest clock selectable in BIOS.
* [Large Drive Support w/Tools (tbplus)][driver-TBPLUS-Full] - Allows Windows 98SE to use hard drives larger than 1TB. (Full TBPlus Pack including DOS partitioning tools)

[Back to Getting Started](../getting-started.md)

[driver-CTMOUSE]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/CTMOUSE.EXE
[driver-r6040dos]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/R6040DOS.ZIP
[driver-PMOUSE]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/PMOUSE.COM
[tool-CWDMIX]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/CWDMIX.EXE
[tool-ANYBIOS]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/ANYBIOS.EXE
[tool-SLOWDOWN]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/SLOWDOWN.ZIP
[driver-TBPLUS-Full]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/TBPLUS/TBPLUS_FULL.zip
[driver-win98-TBPLUS]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/TBPLUS/TBPLUS.zip
[driver-win98-CWD]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/CWD-v286-1998-itx-llama/CWD_DRVS.zip
[driver-win98-R6040]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/r6040_win98/r6040_win98.zip
[driver-win98-USB]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/USB/nusb36e.exe
[driver-crystal-archive]: https://web.archive.org/web/19970607041537/http://www.crystal.com/drivers/audio-d.htm
[os-win98-part1]: https://docs.retrodreams.ca/itxllama/binaries/WIN98/WIN98_1.zip
[os-win98-part2]: https://docs.retrodreams.ca/itxllama/binaries/WIN98/WIN98_2.zip
[os-win98-archive]: https://archive.org/details/win-98-1
[itxllama-repo]: https://github.com/eivindbohler/itxllama/archive/refs/heads/main.zip
[Retrodreams]: https://retrodreams.ca/collections/all
[Retrodreams-FreeDOS]: https://retrodreams.ca/products/preloaded-microsd-card-with-freedos-goodies
[winworldpc-win98]: https://winworldpc.com/download/417d71c2-ae18-c39a-11c3-a4e284a2c3a5
[vogons-thread]: https://www.vogons.org/viewtopic.php?t=93480
[vogons-minidos]: https://www.vogons.org/viewtopic.php?p=1307896#p1307896
[mt32-pi]: https://github.com/dwhinham/mt32-pi
[mt32-pi-control]: https://github.com/gmcn42/mt32-pi-control/tree/main/dos_bin