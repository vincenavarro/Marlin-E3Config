# Marlin-E3Config

My E3 Marlin configuration

Based on [Marlin-2.1.2.1 (Stable)](https://github.com/MarlinFirmware/Marlin/tree/2.1.2.1) and the [example configuration](https://github.com/MarlinFirmware/Configurations/tree/release-2.1.2.1/config/examples/Creality/Ender-3%20Pro/BigTreeTech%20SKR%20Mini%20E3%202.0).

## Build

* Install [Auto Build Marlin](https://github.com/MarlinFirmware/AutoBuildMarlin) extension in Visual Studio Code
* `git clone https://github.com/MarlinFirmware/Marlin.git --branch 2.1.2.1 --depth 1` or [marlinfw.org](https://marlinfw.org/meta/download/)
* Copy the following files to the Marlin folder
  * Bootscreen.h (Optional)
  * _Statusscreen.h (Optional)
  * config.ini (Optional, just ensure it is disabled)
  * Configuration.h
  * Configuration_adv.h
* Go to Auto Build Marlin tab and use STM32F103RE_btt (512K) environment.
* Copy firmware.bin to MicroSD and insert before booting.

## Hardware Assumptions

Original Ender 3 Pro v1.1.4 upgraded with the following modifications required:

* BTT SKR Mini E3 V2.0
* Genuine BLTouch 3.1 w/ 5-Pin (or equivalent) connection connected to PROBE
* Creality-style Touch Mount (`#define NOZZLE_TO_PROBE_OFFSET { -44, -9, 0 }`)
* Generic Filament Runout Detector
* Rewiring ([Reference](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/hardware/BTT%20SKR%20MINI%20E3%20V2.0/Hardware))
  * FAN0 (PC6) → to Part Cooling
  * FAN1 (PC7) → to Hotend
  * POWER (PWR) → to Case Fan

### Soon

* Increased z-axis 2040 extrusion to 500mm (350mm z-axis print area.)

## Misc Settings

Unrelated to Marlin, but the Ender 3 also has an upgraded Dual Drive Gear Extruder. This means that the estep for the extruder must be changed to `144.22`. Find this setting under `Motion → Steps/mm → Esteps/mm`. To calibrate properly [see this video](https://www.youtube.com/watch?v=QnrH2Sk7y40).
