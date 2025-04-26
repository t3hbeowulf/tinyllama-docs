# ITX-Llama - MIDI Options

The ITX Llama is equipped with several distinct options for MIDI playback, including genuine OPL-3 via an add-in module, on-chip emulated OPL-3 provided by the Crystal sound chip, Wavetable header for general MIDI add-on modules and a pair of headers for attaching a Raspberry Pi running [mt32-pi][mt32-pi] for authentic Roland MT-32 support. 

Below is a breakdown of each option and several add-ons that are compatible.

## OPL-3 FM Synthesis Support

1. Out of the box, the Crystal CS4237B sound chip can emulate OPL-3 through its Crystal FM synthesis engine. This is a close approximation to a genuine Yamaha OPL-3 for most titles but has been known to fall short in certain cases. 
1. The ITX Llama offers an OPL-3 header which accepts a [custom OPL-3 board][opl3module] containing an old-stock Yamaha YMF262-M FM synth chip. This will provide a genuine Yamaha OPL-3 sound for games utilizing FM Synthesis. 
    * <p><img src=../images/opl3module.jpg title="OPL3 Module" width=35%></p>

## Roland MT-32 Support

#### Raspberry Pi Zero 2

A Raspberry Pi Zero 2 is capability of emulating a Roland MT-32 using the excellent Munt emulator. To facilitate this as a drop-in feature, the [mt32-pi][mt32-pi] project adds this functionality to a simple Pi Zero 2 and installed directly onto the ITX Llama. Audio is passed through an onboard DAC to the Crystal's Line In.

  * Pros: 
    * provides a near perfect emulation of the Roland MT-32 / CM-32L (Intelligent Mode does require SoftMPU)
    * audio is routed through an onboard DAC to the Crystal sound chip via i2c preventing the need for additional hardware besides the Pi Zero 2 itself and an SD card.
  * Additional features:
    * mt32-pi supports General MIDI using the FluidSynth engine and user-supplied sound fonts. ITX Llama users could technically employ *just* the Pi Zero 2 with mt32-pi in addition to the OPL-3 module to cover nearly all bases of MIDI in early DOS games.
  * Installation:
  * <p><img src=../images/pi-zero2-alignment.jpg title="Pi Zero 2 Alignment" width=50%></p>

#### Raspberry Pi 4

A Raspberry Pi 4 can also be attached in lieu of the Pi Zero 2. This is a much more advanced option but opens the possibility of running a full OS with Munt, FluidSynth and a modified version of the nuked-SC-55 emulator for genuine Roland SC-55 sound support.

  * A 40pin ribbon cable such as an old IDE cable affixed to the pins on board below and to the Raspberry Pi 4 is necessary to use this feature. 
  * At this time, system setup for the Pi 4's OS is an advanced topic that is left up to the user to tinker with.
  * Pin Header: (_below the female Pi Zero 2 header_)
  * <p><img src=../images/som-alignment-1.jpg title="Raspberry Pi 4 header pins visible" width=50%></p>

#### mt32pi Hardware UI

There are a set of headers that allow connecting the an mt32pi Hardware UI (OLED, 4 buttons, optional rotary encoder). This header is connected to the correct GPIO pins on the Raspberry Pi headers to simplify adding a control mechanism. 

  * The header uses the following pins, which are wired one-to-one to an i2c OLED display: [more info][mt32pi-oled-docs] 
    * `SDA` (data), `SCL` (clock), `3v3` (VCC), `GND` (ground)
    * Most OLED displays that specify i2c connections use these four pins.
  * <p><img src=../images/pi-zero2-mt32-ui-header.jpg title="Raspberry Pi - mt32pi UI Header" width=50%></p>
  * The remaining pins are designed for either buttons or a rotary encoder. [more info][mt32pi-control]
    * `B1` and `B2` are "buttons" which control the Synth mode and ROM/Soundfont selection
    * `B3` and `B4` can either be "buttons" or a rotary encoder. These control the output volume of the synth engine.
    * A [rotary encoder can be connected][mt32pi-rotary-encoder] as follows: 
      * `B3 --> DAT` 
      * `B4--> CLK`
      * `GN~D-->GND`

## Wavetable MIDI Support

1. The ITX Llama contains a Wavetable compatible header as well. This can be configured with a variety of Wavetable Synth modules to provide General MIDI support through the Crystal sound chip.
    * This header can be enabled via Jumpers: J25, J26, J27
    * <p><img src=../images/pi-wt.jpg title="PI/WT configuration" width=50%></p>
        * For using a Raspberry Pi (Zero2, 3 or 4) for converting MIDI to analog audio, place the three jumpers to the rightmost position ("PI").  
        * For using a wavetable board, place the jumpers to the leftmost position ("WT").
    * NOTE: In Rev. F, the J27 "Power" jumper was removed. Power is now supplied to both the Wavetable header and the Pi GPIO pins simultaneously.
      
## Wavetable Options

1. **Dreamblaster X8GS SE**
    * **Status:** _Tested, fully operational_
    * General Specs:
        * 128 voice polyphony
        * 1024MB of flash memory for sample sets (divided into 7 banks)
        * "GS" modules include a read-only licensed Roland GS sample set
    * Links:
        * [X8GS][X8GS] - High-end General Purpose MIDI Synth with customizable samples made exclusively for the ITX Llama

1. **Dreamblaster X2 SE / X2GS SE / X2TE**
    * **Status:** _Tested to fit_
    * General Specs:
        * 81 voice polyphony
        * 64MB of flash memory for samples
        * "GS" modules include a read-only licensed Roland GS sample set
    * Links:
        * [X2 SE][X2SE] - General Purpose MIDI Synth with customizable samples
        * [X2GS SE][X2GS-SE] - General Purpose MIDI Synth with customizable samples and an additional licensed Roland SC-55 sample set
        * [X2 TE][X2TE] - "Tiny Edition" of the X2 SE

1. **Dreamblaster X16 / X16GS**
    * **Status:** _Will only fit without a Pi Zero 2 installed_
    * General Specs:
        * 256 voice polyphony
        * 1024MB of flash memory for sample sets (divided into 7 banks)
        * 8MB SDRAM for very high quality DSP effects
        * "GS" modules include a read-only licensed Roland GS sample set
    * Links:
        * [X16][X16] - High-End General Purpose MIDI Synth with customizable samples
        * [X16GS][X16GS] - High-End General Purpose MIDI Synth with customizable samples and an additional licensed Roland SC-55 sample set

[X2SE]: https://www.serdashop.com/X2-SE
[X2GS-SE]: https://www.serdashop.com/X2GS-SE
[X2TE]: https://www.serdashop.com/X2TE
[X16]: https://www.serdashop.com/DreamBlaster-X16
[X16GS]: https://www.serdashop.com/DreamBlaster-X16GS
[X8GS]: https://retrodreams.ca/products/dreamblaster-x8gs-special-edition-wavetable-module-preorder-batch2
[mt32-pi]: https://github.com/dwhinham/mt32-pi
[opl3module]: https://retrodreams.ca/products/llama-opl3-module
[mt32pi-oled-docs]: https://github.com/dwhinham/mt32-pi/wiki/LCD-and-OLED-displays
[mt32pi-control]: https://github.com/dwhinham/mt32-pi/wiki/Control-surface
[mt32pi-rotary-encoder]: https://github.com/dwhinham/mt32-pi/wiki/Control-surface#rotary-encoder
