# ITX-Llama - Running GODS

[GODS][wikipedia] is particularly challenging because it requires a slow CPU and MPU-401 Intelligent Mode to run properly. 
This guide will hopefully help you get this running on your ITX Llama. 

---

## Prerequisites

* MS-DOS or FreeDOS (FreeDOS v1.4 RC2+ has been confirmed to work well)
* EMS activated (2MB minimum)
* SoftMPU configured
* mt32pi selected for sound output, set to MT-32 mode and active
* "slowdown" utility. [(get it here)][tool-SLOWDOWN]

## Configuration

1. ITX Llama CPU Setting: `60MHz`, L1: `disabled`, L2: `disabled`
1. Ensure `SOFTMPU.EXE` and `SLOWDOWN.EXE` are in your GODS game directory
1. Run the following commands:
```
SOFTMPU.EXE /SB:220 /IRQ:7 /MPU:330
SLOWDOWN /P:50
GODS.EXE
```
1. When finished, run to return the Llama to the BIOS configured CPU speed:
```
SLOWDOWN /U
```

[Back to MS-DOS Game Compatibility List](game-compatibility.md) <br>
[Back to Games Index](../index.md)

[wikipedia]: https://en.wikipedia.org/wiki/Gods_(video_game)
[tool-SLOWDOWN]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/SLOWDOWN.ZIP