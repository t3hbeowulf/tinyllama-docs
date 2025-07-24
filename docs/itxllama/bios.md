# ITX-Llama - Vortex86EX BIOS

The ITX Llama uses an open-source BIOS from the coreboot/seabios project. The release builds listed below are tested and intended for use on the ITX Llama Rev E and Rev F. 

## Flashing a new BIOS image

1. Download an image from the list below
1. Copy the ROM file onto a bootable DOS SD card, rename the file to `itxbios.rom`
1. Ensure [anybios.exe][tool-ANYBIOS] is on your SD card.
1. Boot your ITX Llama without any memory managers, conventional memory only.
1. Run the following command from wherever your ROM file is stored:
    ```batch
    anybios.exe w itxbios.rom
    ```

## 2025-06-20 - Quality of Life Improvements

### Image

* [itx-llama-v1-rev-F-20250620-194738.rom][20250620]

#### BIOS Changes

* Add WSS Port x530h selection option
* Set "USB as Fixed Disk" to disabled by default
* Fixed a number of help text messages (including Fan RPM edit notes)
* Add new boot tunes!

#### VFD Changes

* Include CTMouse v2.1, Add CTMouse v2.0 (default), Add PMouse
* Include correct version memory manager programs for DOS 6.22
* Add EMS w/UMBs, XMS w/UMBs, and XMS w/o UMBs to boot options
* Move all drivers to `autoexec.bat`, switch to "devload" instead of `config.sys` for initialization
* Add a menu for selecting system driver loadout on boot
* Added `smartdrv.exe`, `himemx.exe`, `slowdown.exe` and `limitmem.sys` to enhance game compatibility out of the box
* Added `autoexec.hdd` and `config.hdd` files intended to be copied to a DOS HDD install which mimic the memory options of the VFD.
* Optimized remaining space on the DOS 7 VFD, removed unused files
* Improved the "Setup Windows 98" script to match the new Llama-tuned Windows 98 Install ISO.
* Fixed the MiNiDOS VFD image (it was broken on the shipping image)


## 2025-03-02 - Batch #2 Original BIOS

### Image

* [itx-llama-v1-rev-F-20250302-063713.rom][20250302]

#### BIOS Changes

* Add GamePort x201h selection option
* Add "Rev F" labels (Rev E still supported)
* Update copyright year to "2025"
* Incorporate a new dockerized build process for BIOS Images
* Incorporated raw VFD images into build process.

#### VFD Changes

* Added a new 2.88MB VFD for MS-DOS 6.22 with several new tools:
    * CTMOUSE.exe (auto-loads)
    * MOVE.exe
    * EDIT.com
    * QBASIC.exe
    * CWDMIX.exe (Crystal Mixer)
    * VC
    * "Test Suite" for verifying onboard accessories
* Added a new VFD option: MiNiDOS v0.02 with tweaks for the ITX Llama
* Add USB and SATA CD drivers to VFD image
* Add Selection Menu branding to boot menu
* Fixed "Setup Win98" menu option
* Updated MS-DOS 7.1 image to 2.88MB and added several new tools
* Added a working EMM386 NOEMS option to both DOS images
* Added a working EMM386 RAM option to MS-DOS 6.22 image

## 2024-10-14 - Original BIOS

### Image

* [itx-llama-v1-rev-E-20241014-091252.rom][20241014]

[tool-ANYBIOS]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/ANYBIOS.EXE
[20241014]: https://docs.retrodreams.ca/itxllama/binaries/bios/itx-llama-v1-rev-E-20241014-091252.rom
[20250302]: https://docs.retrodreams.ca/itxllama/binaries/bios/itx-llama-v1-rev-F-20250302-063713.rom
[20250620]: https://docs.retrodreams.ca/itxllama/binaries/bios/itx-llama-v1-rev-F-20250620-194738.rom