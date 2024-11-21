# ITX Llama Accessories

Below is a collection of hardware accessories that should work with the ITX Llama in order turn it into an even more capable MS-DOS/Windows PC. If a device needs further testing, it will be noted.

## Optical Disc Drives

1. SATA CD/DVD Drive - **WORKING**
    * Connects directly to the onboard SATA port, appears as a standard optical disc drive.
    * Pros: 
        * Simple hook-up, no fuss
        * Drives are readily available for now
    * Con: 
        * No CD-Audio (SATA ODD models do not have integrated CD Audio DACs)
        * Occupies only onboard SATA port
2. IDE CD/DVD Drive - _requires an adapter_ - **WORKING**
    * Connects to an IDE to SATA adapter and then to the onboard SATA port, appears as a standard optical disk drive.
    * Pros:
        * Has CD-Audio output which can be passed to the onboard Crystal sound card
        * Fairly simple to hook up with required adapters
    * Cons:
        * Requires an IDE to SATA adapter to function. (_ITX Llama has no onboard IDE_)
        * Drives are getting hard to find, old drives are beginning to fail due to age
    * Link(s):
        * Adapter: https://www.amazon.com/Cablecc-Female-Converter-Adapter-Desktop/dp/B081YP2S5R
3. ZuluIDE - _requires an adapter_
    * Connects to an IDE to SATA adapter and then to the onboard SATA port
    * Emulates a CD/DVD drive with ISO or BIN/CUE files stored on microSD card. (https://www.zuluide.com)
    * Pros:
        * Has CD-Audio output for BIN/CUE files, which can be passed to the onboard Crystal sound card
        * No moving parts!
        * Fairly simple to hook up with required adapters
    * Cons:
        * Requires an IDE to SATA adapter to function. (_ITX Llama has no onboard IDE_)
        * Does not support copy-protected images
        * Has a very rudimentary image selection mechanism as of 2024-11-21.


## Floppy Disk Drives

1. GoTek Floppy Emulator - _requires an adapter_
    * Connects to a Floppy to USB adapter and to the rear USB ports.
    * Emulates a 720k/1.44MB Floppy drive with images stored on USB.
    * Link(s):
      * Adapter: https://www.amazon.com/KOOBOOK-1-44MB-Floppy-Connector-Adapter/dp/B07WCRF9H3

## External Joystick / MIDI Port

1. DB15 to MIDI In/Out
    * Link: https://www.serdashop.com/DB15MIDI
1. DB15 Splitter (_for Joystick and MIDI_)
    * Link: https://www.serdashop.com/DB15-Doubler-Solder-Kit