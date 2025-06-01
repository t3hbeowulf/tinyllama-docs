# ITX-Llama - Running ScummVM Games

While starting Quest for Glory 4 (ScummVM), game startup takes a while and the mt32-pi gets "hung". 
This guide will hopefully help you get games like this running on your ITX Llama.

---

## Prerequisites

* MS-DOS or FreeDOS
* EMS activated (2MB minimum)
* SoftMPU configured
* mt32pi selected for sound output, set to MT-32 mode and active

## Configuration

1. Ensure `SOFTMPU.EXE` is in your game directory
1. Run the following commands:
```
SOFTMPU.EXE /SB:220 /IRQ:7 /MPU:330
set SDL_AUDIODRIVER=waveout
```

[Back to MS-DOS Game Compatibility List](game-compatibility.md) <br>
[Back to Games Index](../index.md)