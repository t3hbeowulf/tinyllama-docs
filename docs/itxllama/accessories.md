# ITX-Llama - Accessories

Below is a collection of hardware accessories that should work with the ITX Llama in order turn it into an even more capable MS-DOS/Windows PC. If a device needs further testing, it will be noted.

## Optical Disc Drives

1. **SATA CD/DVD Drive**
    * **Status:** Verified to work on ITX Llama
    * Connects directly to the onboard SATA port, appears as a standard optical disc drive.
    * Pros: 
        * Simple hook-up, no fuss
        * Drives are readily available for now
    * Cons: 
        * No CD-Audio (SATA ODD models do not have integrated CD Audio DACs)
        * Occupies only onboard SATA port

1. **IDE CD/DVD Drive** - _requires an adapter_
    * **Status:** Verified to work on ITX Llama
    * Connects to an IDE to SATA adapter and then to the onboard SATA port, appears as a standard optical disk drive.
    * Pros:
        * Has CD-Audio output which can be passed to the onboard Crystal sound card
        * Fairly simple to hook up with required adapters
    * Cons:
        * Requires an IDE to SATA adapter to function. (_ITX Llama has no onboard IDE_)
        * Drives are getting hard to find, old drives are beginning to fail due to age
    * Link(s):
        * Adapter: [IDE to Sata][IDEtoSata]

1. **ZuluIDE** - _requires an adapter_
    * **Status:** Verified to work on ITX Llama
    * Connects to an IDE to SATA adapter and then to the onboard SATA port
    * Emulates a CD/DVD drive with ISO or BIN/CUE files stored on microSD card. [ZuluIDE Homepage][ZuluIDE]
    * Pros:
        * Has CD-Audio output for BIN/CUE files, which can be passed to the onboard Crystal sound card
        * No moving parts!
        * Fairly simple to hook up with required adapters
    * Cons:
        * Requires an IDE to SATA adapter to function. (_ITX Llama has no onboard IDE_)
        * Does not support copy-protected images
        * Has a very rudimentary image selection mechanism as of 2024-11-21.
    * Add-ons:
        * With a Pi Pico/DAC board populated with a Pi Pico W, you can add remote image management to the ZuluIDE
        * The DAC board also enables passing CD Audio to the onboard Crystal sound chip
    * Link(s):
        * Adapter: [IDE to Sata][IDEtoSata]
    * Additional Configuration Information for the `zuluide.ini` file:
``` ini title="zuluide.ini"
[ide]
max_udma = -1
max_pio = 3
max_blocksize = 4096
device = CDROM
```

1. **USBODE** 
    * **Status:** Verified to work on ITX Llama
    * Connects to a Raspberry Pi Zero 2 W / or Raspberry Pi Zero W through USB
    * Emulates a CD/DVD drive with ISO files stored on microSD card. [USBODE Homepage][USBODE-PAGE]
    * Pros:
        * No moving parts!
        * Fairly simple to hook up
        * Simple Setup
        * Uses inexpensive off-the shelf parts
    * Cons:
        * Does not support copy-protected images
        * Requires Wi-Fi to utilize (change images via a webpage from a separate device, like a smartphone)
        * Open Source project may have bugs
    * Notes:
        * The author of this project continues to work on it, and will hopefully provide a solution for CD Audio in the futur (this may require an addon)

## Floppy Disk Drives

1. GoTek Floppy Emulator - _requires an adapter_
    * **Status:** As of 2025-01-30, this is NOT working on the ITX Llama
    * Connects to a Floppy to USB adapter and to the rear USB ports.
    * Emulates a 720k/1.44MB Floppy drive with images stored on USB.
    * Link(s):
      * Adapter: [Floppy (34pin) to USB][FloppytoUSB]
2. 3.5" Floppy Drive - _requires an adapter_
    * **Status:** As of 2025-01-30, this is NOT working on the ITX Llama
    * Connects to a Floppy to USB adapter and to the rear USB ports.
    * Link(s):
      * Adapter: [Floppy (34pin) to USB][FloppytoUSB]

## External Joystick / MIDI Port

1. Adapt [DB15 to MIDI In/Out][DB15toMIDI]
1. [DB15 Splitter][DB15splitter] (_for Joystick and MIDI_)

## Keyboard / Mouse

1. Native PS/2 ports are provided for keyboard and mouse support
1. Optionally, the PS/2 ports can be disabled and a pair of dedicated USB ports can adapt themselves to PS/2 internally.
    * This allows modern USB peripherals to appear as PS/2 devices to the OS.

[ZuluIDE]: https://www.zuluide.com
[USBODE-PAGE]: https://github.com/danifunker/usbode
[IDEtoSata]: https://www.amazon.com/Cablecc-Female-Converter-Adapter-Desktop/dp/B081YP2S5R
[FloppytoUSB]: https://www.amazon.com/KOOBOOK-1-44MB-Floppy-Connector-Adapter/dp/B07WCRF9H3
[DB15toMIDI]: https://www.serdashop.com/DB15MIDI
[DB15splitter]: https://www.serdashop.com/DB15-Doubler-Solder-Kit