# Getting Started with your ITX-Llama

Congratulations! You have chosen an excellent modern platform for experiencing many classic MS-DOS and early Windows 98 Games and software. The following guide will help you get started with setting up your ITX-Llama for the first time. 

---

## Unbox and Assembly

Each ITX-Llama shipped from the [Retrodreams.ca Shop][Retrodreams] should come with the following installed:

* **Modem:** Wemos D1 Mini ESP8266 for "modem-over-WiFi". Please review the [modem's manual][modem-manual]

Optionally, you may have elected to include the following accessories:

* Vortex86EX System-on-Module (CPU, RAM, L1/L2 Cache for your Llama)
* Raspberry Pi Zero 2 w/mt32pi installed
* Dreamblaster X8GS Wavetable MIDI module
* Yamaha OPL-3 Module
* Official ITX-Llama case
* An SD card with FreeDOS preloaded

---

### Accessories

1. Vortex86EX System-on-Module
    * Contains the CPU, chipset, RAM, BIOS and NVRAM for settings
    * <p>
         <img src=../images/SoM-top.webp title="Vortex86EX" width=25%>
         <img src=../images/SoM-bottom.webp title="Vortex86EX" width=29%>
      </p>
2. Yamaha OPL-3 MIDI Module
    * Supports high quality FM Synthesis using a genuine Yamaha OPL-3 synthesis chip
    * <p>
         <img src=../images/OPL3-top.webp title="OPL3" width=25%>
         <img src=../images/OPL3-bottom.webp title="OPL3" width=25%>
      </p>
3. Raspberry Pi Zero 2 w/mt32pi installed
    * Emulates Roland MT-32/CM-32L via Munt
    * Supports General MIDI playback via Fluidsynth and Sound Fonts (*.sf2)
    * <p>
         <img src=../images/pi-zero2-close-up.webp title="mt32pi" width=25%>
      </p>
4. Dreamblaster X8GS Wavetable MIDI module
    * Contains genuine licensed Roland SC-55 samples in ROM
    * 128 voice polyphony, 1 GB of flash memory for additional samples
    * <p>
         <img src=../images/X8GS_top_wb.webp title="Dreamblaster" width=25%>
         <img src=../images/X8GS_bottom_wb.webp title="Dreamblaster" width=25%>
      </p>
5. The Official ITX Llama Case
    * Custom-designed and thoroughly tested to fit the ITX-Llama
    * <p>
         <img src=../images/itx-llama-case.webp title="itxllama case" width=25%>
         <img src=../images/itx-llama-case-2.webp title="itxllama case" width=45%>
      </p>
6. FreeDOS SD Card tuned for the ITX Llama
    * Pre-loaded with FreeDOS v1.4 RC and tested to work on the ITX-Llama
    * If you purchased an SD card, [click here](getting-started/freedos-sdcard.md) for an important message.
    * <p>
         <img src=../images/gs-freedos-sd.jpg title="itxllama case" width=35%>
      </p>

---

## Jumper Configuration

See [Configuring Jumpers](getting-started/jumpers.md) for detailed information on hardware configuration.

---

## Case Assembly

See [Assembling Your Official Case](getting-started/case-assembly.md) for detailed information on assembling your Official ITX Llama Case.

---

## First Boot Tour

See [First Boot](getting-started/firstboot.md) for what happens when you first boot your ITX-Llama

---

## Setup and Installation

See [Setup](getting-started/setup.md) for detailed information on installing an operating system.

* [DOS Drivers](getting-started/setup.md#dos-drivers)
* [Windows 98 Drivers](getting-started/setup.md#windows-98-drivers)
* [Tools](getting-started/setup.md#tools)

[Retrodreams]: https://retrodreams.ca/collections/all
[winworldpc-win98]: https://winworldpc.com/download/417d71c2-ae18-c39a-11c3-a4e284a2c3a5
[vogons-thread]: https://www.vogons.org/viewtopic.php?t=93480
[vogons-minidos]: https://www.vogons.org/viewtopic.php?p=1307896#p1307896
[mt32-pi]: https://github.com/dwhinham/mt32-pi
[mt32-pi-control]: https://github.com/gmcn42/mt32-pi-control/tree/main/dos_bin
[modem-manual]: https://docs.retrodreams.ca/itxllama/binaries/MANUALS/MODEM.PDF