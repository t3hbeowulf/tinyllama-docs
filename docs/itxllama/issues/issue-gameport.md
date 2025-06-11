# Known Issue - GamePort functionality limitations

Batch #1 and #2 (thru Rev F) have some unintended limitations in functionality for the GamePort, particularly in MS-DOS.

## Problem Description

The GamePort on the ITX-Llama interfaces with the Crystal CS4372B sound chip. During the design, it was observed that Crystal shares pins with other functions and a decision was made to limit joystick support to 2 axis, 2 buttons (Joystick #1) so that other features could be enabled. The pins used to communicate with the External FM Synth and S/PDIF audio output are also used for Buttons #3 and #4 of "Joystick #2". _As an unintended consequence, it was discovered that the Crystal chip mirrors/ghosts the signal data reserved for S/PDIF and the External FM module onto Buttons #3 and #4 despite  "Joystick #2" being disabled. 

## Symptom

* Joystick tests show excessive activity on buttons #3 and #4. 
* Games which use those buttons interact unexpectedly, skip cut scenes or behave erratically. 
* Calibration and button reassignment is not possible as the erratic activity skips or assigns buttons incorrectly.

## Workaround

Disable the GamePort by forcing a mismatch in the port assignment. 

* In BIOS: Select Port 208h for the GamePort
* In Autoexec.bat: Ensure SET BLASTER has `J200` or `J0` (if using the [UNISOUND](https://www.vogons.org/viewtopic.php?t=72553) driver) at the end.

This mismatch will effectively disable the GamePort in DOS and prevent erratic button presses from causing games to misbehave. 