# Getting Started - Setting up Windows 98

The following guide will help you get started with setting up Windows 98 on your ITX-Llama. 

---

### Recommended Windows 98 Installation Procedure

1. Prepare a Windows 98 CD.
    * An ISO containing the necessary setup files is here: [Slip-streamed Install Files][os-win98-archive]
    * These Windows 98 installation files contain ITX-Llama specific drivers and the <8GB corruption fix slip-streamed into the installation.
1. Choose the "Windows 98 (DOS 7.1)" VFD (Virtual Floppy Disc) in BIOS
1. Insert a blank SD card (128GB or less is ideal), or SATA SSD
1. Ensure you're booting from "Windows 98 (DOS 7.1)" VFD by pressing `ESC` during start-up and selecting the Virtual Floppy image.
1. Format your chosen fixed storage device as normal. See [#MS-DOS Installation].
1. Restart your ITX-Llama
1. Ensure you're booting from "Windows 98 (DOS 7.1)" VFD by pressing `ESC` during start-up and selecting the Virtual Floppy image.
1. Select the "Setup Windows 98" option.  _setup should begin._

---

### Alternative Windows 98 Installation Procedure (SATA SSDs)

1. Prep SDCard as installer:
    a.  Extract ISO of windows 98 SE to root of SDCard
    b.  Download the [Windows 98 ITX-Llama Driver Pack][win98-driverpack] and extract the ZIP file, place the folder WIN98-DRV onto the SDCard
    c.  Place SDCard into ITX Llama
1. Boot ITX Llama, change BIOS settings so SATA drive is first priority (F1 to enter BIOS)
1. Under Disk Settings, (use the left and right arrow keys to switch between panes) set :
    a.  Boot Order to anything with SATA first. 
    b.  Virtual Floppy to Windows 98 (DOS 7.1)
    c.  USB as Fixed Disks: Disabled
1. Save settings with `F10`, this will save and reboot the BIOS settings
1. Press `ESC` during boot-up and choose the Win98 Boot Disk
1. Choose option 3 `Start ITX-Llama without CD-ROM Support`
1. Partition the SATA disk using `xfdisk`:
    a.  Follow the instructions onscreen in order to partition the hard disk
    b.  Once complete, reboot the computer and follow steps 5-6 again
1. Once rebooted, try to navigate to the C:, it should give an error saying the disk is not formatted. Press `A` to abort, then go back to the A: and run `format C:`
1. After formatting C:, let’s copy the windows 98 files onto the SATA disk. First, we need to extract xcopy  files from the media, go to the WIN98 folder on the D:, then use the following command `extract /a win98_47.cab xcopy*.*`
1. Create a win98 folder on the C: (this will hold the installation files), `md C:\win98`
1. Copy the files over, `xcopy /a /s *.* C:\win98 `
1. Create a folder on the C: for the itx-llama patches (we will need to use these soon), `md C:\itxdrvs`
1. Copy the files from the itx-llama patches folder to the C:, don’t leave the win98 folder: `xcopy /a/s \WIN98-DRV\*.* C:\itxdrvs\` (remember to use tab completion in order to auto-fill the folder names in correctly)
1. Launch `setup.exe` in C:\win98 and complete the installation...
1. The system will reboot from GUI install mode. This is where we need to install the ITX Llama drivers packages. When the system tells you to remove the floppy disks and reboot, during that reboot start pressing F8 to force Windows to bring up the boot menu. 
1. Select `Safe-Mode Command Prompt Only` (Shift + F5)
1. In the command prompt: `cd \itxdrvs\tbplus` then `install C:\windows`
1. Eject the SDCard, then reboot the system
1. Windows should complete without any issues at this point. 

The author of this section notes there are incompatibilities with the driver `esdi_506.pdr` when Windows 98 is being loaded. This issue is caused when booting from an SSD, and an SDCard is inserted. In some configurations this issue can be resolved by creating an extended partition on the SSD. Otherwise, try to boot with the sdcard ejected.

---
### Modem Configuration in Windows 98

After finalizing configuration of the Windows 98 installation, download the [Modem INF file][mdmllama] then complete the following instructions:

1. Navigate to to system -> device manager
1. Find the modem on com2, go to properties (if none is installed, go ahead and add a new unlisted modem, and point it to the `mdmllama.inf` which was downloaded earlier). Set the baud rate to `300 baud`
1. Select update driver, browse to `mdmllama.inf` (downloaded above).
Installing this driver will enable higher speeds baud speeds.
1. Go into hyperterminal (under accessories)
    - By default the modem will be set to `300 baud`
    - set it to com2
    - turn flow control to xon/off (software)
    - connect 
1. Type in the following commands into hyperterminal:
    - `AT` <-- _should respond with 'OK'_ 
    - `AT$SSID=wifinetwork`
    - `AT$PASS=wifipass`
    - `ATC1`
    - `AT$SB=115200`
1. disconnect hyperterminal
1. Go back into device manager change settings to have baud of `115200 `
1. reconnect in hyperterminal to verify the baud rate is set correctly.
1. Once settings have been verified, save the settings with the following command
    - `AT&W`
1. Go to start -> accessories -> communications -> dial-up networking 
1. Create new connection 
    - number is `PPP` or `777` 
1. Save your connection 
1. Double click to connect

---
### Windows 98 Performance Tuning

For using Windows 98 on any medium especially SSDs and SD card:

* Install T1 patch in safe mode _(not necessary if you're using the default instal media above, it's already integrated)_
* Enable DMA for your disks
* Disable virtual memory _(saves write-cycle/wear on your SD Card/SSD)_
* Disable scheduled tasks _(esp. anti virus check and defrag jobs)_

---
### Known Issues

#### 256 Color Mode on ATI Cards

There are known issues with the ATI drivers running on the ITX Llama when the driver is configured for 640x480 or 800x600 at 256 color depth. This issue appears in Windows 95, 98, 2000 and XP. A workaround driver has been included [here][ati-drivers-modified]. The ITX Llama team is still analyzing the issue and will provide updates here once any further findings are reported. Be aware there have been some reports of users after installing the ATI driver, even after shifting back to a Voodoo 3 card, where they continued to experience the 256 color mode bug.

#### Running Sierra games through SCUMMVM

SCUMMVM provides a mainline Windows 98 version still. 
That said, if you're running into audio issues, please add the following line to your `autoexec.bat`: 
``` batch title="autoexec.bat"
set SDL_AUDIODRIVER=waveout
```

#### Mixer / Level issues with MIDI in Windows 98

In case anyone else is having issues with midi audio in Windows. 
Stage the Crystal driver folder to `C:\Crystal` Add these two lines to your `autoexec.bat`:

``` batch title="autoexec.bat"
SET BLASTER=A220 I7 D1 T5 P330 J201
C:\CRYSTAL\CWDMIX /M=13,13 /W=13,13 /L=13,13 /X=1 /F=13,13 /C=13,13 /I=L
```

#### Disable S/PDIF output in Windows 98

Windows 98 does not pay attention to the BIOS/DOS S/PDIF settings and enables it on driver installation. You can brute-force correct this if you never want to use the S/PDIF output by performing the following actions: 

1. In `C:\SETUP\lamawin98drv\CWD-v286-1998-itx-llama\` edit `cwdaudio.inf`
1. Find the line that reads `HKR,Config\MIXER,EnableDSPSerialPort,,4`
1. Edit that to read `HKR,Config\MIXER,EnableDSPSerialPort,,0`
1. Open device manager and locate Crystal PnP Audio System CODEC
1. Click Properties -> Driver -> Update Driver
1. Point the wizard at the driver folder. _You'll need to do this for several files that it requests._

Alternatively, you can disable S/PDIF by setting this registry key or patching the registry with the following file:
``` ini title="Disable_EnableDSPSerialPort.reg"
REGEDIT4

[HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Class\MEDIA\0000\Config\MIXER]
"EnableDSPSerialPort"="0"
```

---

### Windows 98 Drivers
* [Windows 98 Drivers](setup.md#windows-98-drivers)

---

[Back to Setup](setup.md) <br>
[Back to Getting Started](../getting-started.md)

[os-win98-archive]: https://archive.org/download/win98se4llama/Win98SE-4-llama-r2.iso
[win98-driverpack]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/WIN98-DRV.ZIP
[itxllama-repo]: https://github.com/eivindbohler/itxllama/archive/refs/heads/main.zip
[Retrodreams]: https://retrodreams.ca/collections/all
[Retrodreams-FreeDOS]: https://retrodreams.ca/products/preloaded-microsd-card-with-freedos-goodies
[winworldpc-win98]: https://winworldpc.com/download/417d71c2-ae18-c39a-11c3-a4e284a2c3a5
[vogons-thread]: https://www.vogons.org/viewtopic.php?t=93480
[vogons-minidos]: https://www.vogons.org/viewtopic.php?p=1307896#p1307896
[mt32-pi]: https://github.com/dwhinham/mt32-pi
[mt32-pi-control]: https://github.com/gmcn42/mt32-pi-control/tree/main/dos_bin
[ati-drivers-modified]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/llama-ATIDrivers-disable256Colors-6-2_wme_dd_cp_30314.zip
[mdmllama]: https://docs.retrodreams.ca/itxllama/binaries/WIN98-drivers/mdmllama.inf
