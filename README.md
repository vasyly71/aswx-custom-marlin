# Marlin 3D Printer Firmware customized for Artillery Sidewinder X1

This project forked from [Marlin](https://github.com/MarlinFirmware/Marlin) to maintain my customizatio for [Artillery Sidewinder X1](https://artillery3d.com/artillery-sidewinder-x1-sw-x1-3d-printer-300x300x400mm-large-plus-size-high-precision-dual-z-axis-tft-touch-screen-p0013.html). 

## Specifics of configuration

Most of configuratio parameters i used from repository [pinguinpfleger/ASWX1-FW-MOD](https://github.com/pinguinpfleger/ASWX1-FW-MOD).

Changes for MBL i figured from  ["Sidewinder X-1 Marlin 2.0.5.3 with MBL + TFT"](https://forum.fulament.com/t/m1hyn1l). It also includes a nice firmware for TFT screen that utilizes MLB.

Besides technical specifics of Artillery Sidewinder X1 (drivers, voltage etc) following elements also configured:
   * PID for extruder, please note that i use original E3D heater cartridge, thermister and volcano block with all metal hotend.
   * PID for bed for 70C
   * Calibrated value for extruder steps/mm
   * BAUDRATE 115200 - with higher speeds i had a lot of checksum errors while using [Octoprint](https://octoprint.org/). __Important__: Seems like same BAUDERATE should be configured for TFT screen, otherwise it is not able to connect to printer.  
   * Enable CLASSIC_JERK
   * Enable S_CURVE_ACCELERATION
   * Enable PROBE_MANUALLY
   * Enable MESH_BED_LEVELING
      * MESH_INSET 15
      * Mesh size: 3X3
   * Enable BABYSTEPPING
   * Enable RESTORE_LEVELING_AFTER_G28
   * Enable EEPROM_SETTINGS
   * Enable LIN_ADVANCE, but LIN_ADVANCE_K is set to 0.00 (effectivly disbles it)
   * 




## Building 
To this firmware is based on Marlin 2 and you will need Arduino IDE 1.8.8 or newer or PlatformIO. Detailed instructions on [Building Marlin with Arduino](https://marlinfw.org/docs/basics/install_arduino.html) and [Building Marlin with PlatformIO](https://marlinfw.org/docs/basics/install_rearm.html) can be used to build this firmware.

## License

This software is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use this firmware as the driver for your open or closed-source product, you must keep it open, and you must provide your compatible source code to end users upon request. The most straightforward way to comply with the license is to make a fork of this software on Github, perform your modifications, and direct users to your modified fork.

While we can't prevent the use of this code in products (3D printers, CNC, etc.) that are closed source or crippled by a patent, we would prefer that you choose another firmware or, better yet, make your own.
