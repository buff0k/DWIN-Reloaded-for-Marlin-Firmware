# DGUS-reloaded - DWIN Project Updated

DWIN T5UID1 touchscreen firmware for 3D printers running Marlin, based on the original by [Neo2003](https://github.com/Neo2003/DGUS-reloaded/) with a minor fix and more risk.

Requires using the latest 2.1_bugfix of Marlin to work properly, which can be found in [the official repository](https://github.com/MarlinFirmware/Marlin).

## Disclaimer
**This software is provided without any warranty. You are solely responsible for your use of it.**

## Features

This firmware was inspired by Neo2003's project, based on Creality printers' touchscreen firmware. Some features include:

* Status message available on most screens
* Z offset, manual and automatic leveling
* User confirmation screen (used by the filament runout procedure for example)
* Power loss recovery
* Custom G-code input
* PID autotuning
* Volume adjustment (saved to EEPROM)
* Brightness adjustment (saved to EEPROM)
* EEPROM reset shortcut
* BLTouch reset shortcut (if a BLTouch is installed)
* Print statistics (on the informations screen)
* Playing sounds using M300 (the frequency parameter is the index of the audio file)

I had to rework some issues with the DWIN Set and recompile it using a newer version of DGUS, as there was an issue with Neo2003's descriptors and some memory overruns/underruns due to his not compiling for the newer OS version he recommended to get G-Code working.

## Compatibility
This firmware **should** be compatible with printers equipped with the following hardware:

* 480x272 DWIN T5UID1 touchscreen
* Single extruder
* Heated bed
* Single controllable fan
* Bed leveling sensor (including a BLTouch)

It **could** also work on machines equipped with more hardware (dual extruder, etc.) but will lack on-screen controls for such hardware.

Testing has been done on the following machine:

* Creality CR-10 Max

## Prerequisites
You have to compile and flash this [2.1 bugfix version of Marlin](https://github.com/MarlinFirmware/Marlin) with `DGUS_LCD_UI RELOADED` defined in the configuration.

Example Marlin configurations are available in [this repository](https://github.com/MarlinFirmware/Configurations).

## Installing - Important - Risks Bricking your Screen if a Power Failure occurs

1. Download the DWIN_SET.zip archive from this repo.
2. Extract the contents of the archive, you should have a folder called DWIN_SET, including the two BIN files for the OS and Screen Hardware.
3. Prepare your SD Card by formatting the micro SD card to FAT32 with 4096 byte sector side (these parameters are strictly required for the procedure to work).
4. Copy the DWNI_SET folder exactly to the sd Card (That means the DWIN_SET folder will be on the root of the sd Card).
5. Unmount and unplug the sd Card.
6. Turn off and unnplug your printer (both power and USB).
7. You need to access the micro SD slot on the back of the touchscreen (not the one on the printer mainboard), you will have to remove the cover plate to gain access.
8. Insert the micro SD card in the slot on the touchscreen.
9. Plug the printer's power cable back (and only the power cable) and turn the printer on.
10. After a few second, the screen's background will turn blue and the flashing procedure will begin.
11. Do not cut power to the printer while the flashing procedure is running!
12. When the procedure ends, you will be back on the page with a blue background. There will be an END message at the top and you'll be presented with a summary of what was flashed.
13. At this point, you can turn your printer back off, remove the micro SD card from the touchscreen and reassemble your printer if you had to disassemble it previously.

## Modification / Compilation
You can make modifications to the firmware by opening the `DWprj.hmi` file in **DGUS Tools**.

After finishing your modifications, you will need to press the *Generate* button to create the 3 required binary files.

You can then run the rename script and flash your touchscreen using the resulting `DWIN_SET` folder.

## Credits
| Material                                                                       | Author                                                    | Modified | License                                                               |
|:------------------------------------------------------------------------------:|:---------------------------------------------------------:|:--------:|:---------------------------------------------------------------------:|
| [Marlin logo](https://github.com/MarlinFirmware/MarlinDocumentation)           | [MarlinFirmware](https://github.com/MarlinFirmware)       | Yes      | [GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)                     |
| [Feather icons](https://feathericons.com/)                                     | [Cole Bemis](https://twitter.com/colebemis)               | Yes      | [MIT](https://github.com/feathericons/feather/blob/master/LICENSE)    |
| [3D Printing Line icons](https://www.iconfinder.com/iconsets/3d-printing-line) | [Sam Baines](https://www.iconfinder.com/conceptbaines)    | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/legalcode)    |
| [Fan icon](https://thenounproject.com/term/fan/1153915/)                       | [Atif Arshad](https://thenounproject.com/atifarshad/)     | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [Snow icon](https://thenounproject.com/term/snow/1959859/)                     | [Shashank Singh](https://thenounproject.com/rshashank19/) | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [Electric Motor icon](https://thenounproject.com/term/electric-motor/2734486/) | [Verry](https://thenounproject.com/verry.dsign.creative)  | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [Probe icon](https://thenounproject.com/term/probe/1841345/)                   | [Mohamed Mbarki](https://thenounproject.com/mb.icons)     | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [Wheel icon](https://thenounproject.com/term/wheel/92430/)                     | [Deivid Sáenz](https://thenounproject.com/deivid.saenz)   | Yes      | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [Ruler icon](https://thenounproject.com/term/ruler/1738925/)                   | [Three Six Five](https://thenounproject.com/365)          | -        | [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/legalcode) |
| [DGUS-reloaded](https://github.com/Neo2003/DGUS-reloaded/)                     | [Neo2003](https://github.com/Neo2003)                     | Yes      | [GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)                     |


## License
[GPLv3](http://www.gnu.org/licenses/gpl-3.0.html)
