# Klipper config for Fysetc Voron 0.2 R1 V1.1 Pro
My Klipper config as well as a few notes on how to configure the slicer.  
The printer is built from [this kit](https://www.aliexpress.com/item/1005008626712100.html).

## Hardware Components
* Mainboard: **Fysetc Catalyst v2.1**
* * MCU (Main Control Board): **STM32F446**
* * Steppers: **TMC2209**
* Host computer: **CM68** (Rockchip RK3568 2GB+32GB) (RPi compute module formfactor) mounted on the Catalyst board
* Tool head board: **M36**
* * MCU: **STM32F072**
* * Accelerometer: **ADXL345**
* Hotend: [**Sailfish High Flow**](https://www.fysetc.com/products/fysetc-v6-hotend-sailfish-high-flow-speed-v6-j-head-kit-extrude-head-for-cr-10-cr10s-ender-3-ender3-pro-voron-2-4-3d-printer-hotend)
* Display:[**Fysetc Voron V0 1.3" OLED**](https://www.fysetc.com/products/fysetc-voron-v0-1-3-inch-oled-display-screen-smart-display-for-raspberry-pi-3-b-voron-v0-3d-printer-accessories)

## Configuration
Add a Voron v0 using the setup wizard

### A better print_start macro
[Github link](https://github.com/jontek2/A-better-print_start-macro)

#### Klipper Macro
It's already added in macros.cfg

#### Slicer

PrusaSlicer / Super-Slicer: `Printer settings` --> `Custom g-code` -> `Start g-code`
```
M104 S0 ; Stops PrusaSlicer from sending temp waits separately
M140 S0
print_start EXTRUDER=[first_layer_temperature[initial_extruder]] BED=[first_layer_bed_temperature] CHAMBER=[chamber_temperature]
```

`Print settings` --> `Output options` --> `Output filename format`:
```
{input_filename_base}_{print_time}_{nozzle_diameter[0]}_{filament_type[0]}_{printer_model}.gcode
```


### [Configure klipper for a new printer](readme-configure-new-printer.md)

### Various notes:
Default target_temp: 40
For CM68_fan set: `target_temp: 60`

