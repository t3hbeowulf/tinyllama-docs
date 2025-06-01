# ITX-Llama - Hardware Compatibility Matrix

## Graphics
| Family | Model         | Tested DOS (y/n) | Tested Win98 (y/n) | Notes                                    |
| :----: | :-----------: | :--------------: | :----------------: | :--------------------------------------- |
| ATI    | Radeon 7500   | 🟩 - y           | 🟨 - y             | Win98: (256 color mode issues observed)  |
| ATI    | Radeon 9250   | 🟩 - y           | 🟨 - y             | Win98: (256 color mode issues observed)  |
| 3DFx   | Velocity 100  | 🟩 - y           | 🟩 - y             |                                          |
| 3DFx   | Voodoo 3 1000 | 🟩 - y           | 🟩 - y             |                                          |
| 3DFx   | Voodoo 3 2000 | 🟩 - y           | 🟩 - y             |                                          |
| 3DFx   | Voodoo 5 5500 | 🟩 - y           | 🟩 - y             |                                          |
| nVidia | Riva 128      | 🟩 - y           | 🟥 - n             | Win98: Driver won't initialize           |
| nVidia | TNT           | 🟩 - y           | 🟥 - n             | Win98: Driver won't initialize           |
| nVidia | TNT2          | 🟩 - y           | 🟥 - n             | Win98: Driver won't initialize           |
| S3     | Savage4       | 🟩 - y           | 🟥 - n             | Win98: Black screen after driver install |
| Matrox | G100          | 🟩 - y           | 🟥 - n             | Win98: Black screen after driver install |

## Wavetable Options
| Module    | MIDI Type                        | Connector   | Notes                                       |
| :----:    | :------------------------------: | :---------: | :------------------------------------------ |
| X2GS      | GM/GS Wavetable                  | Wavetable   | Fits without issue                          |
| **X8GS**  | GM/GS Wavetable                  | Wavetable   | Fits without issue, exclusive to ITX Llama  |
| X16GS     | GM/GS Wavetable                  | Wavetable   | Fits but overlaps Pi headers                |
| OPL-3     | FM Synth                         | OPL Header  | Fits without issue                          |
| Pi Zero 2 | MT-32 / Sound Font               | GPIO Header | Fits without issue                          |
| Pi 4      | MT-32 / Sound Font / Nuked SC-55 | GPIO Header | Fits when attached to a 40pin cable         |
