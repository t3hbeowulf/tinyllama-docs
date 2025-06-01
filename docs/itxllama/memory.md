# MS-DOS Memory Management

### Notes

1. The EMM386.EXE default detection code searches for the presence of a Token Ring Network adapter, which may cause some computers to hang. In such cases use the `NOTR` parameter to disable this search. (MS-DOS 6.xx and up, only) [source][NOTR-source]
1. SMARTDRV.exe seems to improve UMB utilization stability, Load it after Himem but before EMM386 in config.sys
  * [Fixing EMM386.exe with SMARTDRV and Double Buffering][msdos-doublebuffer]
1. EMS, particularly with respect to upper memory blocks, appears to be more stable under native MS-DOS 6.22 or FreeDOS v1.4 w/JEMMEX.

[NOTR-Source]: https://secrets.mysfyts.com/index.asp?Page=Emm
[win98-bootdisk-contents]: https://www.allbootdisks.com/disk_contents/98.html
[msdos8-bootdisk-contents]: https://www.allbootdisks.com/disk_contents/dos.html