# ITX-Llama - Running Blood

[Blood][wikipedia] requires some tweaks to get running on a Voodoo3 in MS-DOS 
This guide will hopefully help you get this running on your ITX Llama. 

---

## Prerequisites

* MS-DOS or FreeDOS (FreeDOS v1.4 RC2+ has been confirmed to work well)
* Voodoo3

## Configuration

1. ITX Llama CPU Setting: `300MHz`, L1: `enabled`, L2: `enabled`
1. Copy `Glide2x.ovl` from a 3dfx driver archive into the game folder.
1. Add the following variables to a batch runner for the game:

``` batch title="run.bat"
set BUILD_640x480=1
set BUILD_CONVTEXTURES=1
set BUILD_GAMMA=1.0
set BUILD_RESAMPLE=1
set BUILD_BRIGHTNESS=0.9
set BUILD_NOPAL=0
set BUILD_NOFOG=0
set BUILD_TRICOUNT=0
set BUILD_FPS=0
set BUILD_VERSION=0
set BUILD_MRED=200
set BUILD_MGREEN=200
set BUILD_MBLUE=255

blood.EXE
```

These should optimize the game for running on a 3Dfx card with better gamma and image quality.


[Back to MS-DOS Game Compatibility List](game-compatibility.md) <br>
[Back to Games Index](../index.md)

[wikipedia]: https://en.wikipedia.org/wiki/Blood_(video_game)
[tool-SLOWDOWN]: https://docs.retrodreams.ca/itxllama/binaries/DOS-utils/SLOWDOWN.ZIP