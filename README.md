# These configurations are untested, I have switched to Klipper

# Marlin Configurations

[MarlinFirmware/Marlin v2.1.1](https://github.com/MarlinFirmware/Marlin/releases/tag/2.1.1) configuration files for my modded Creality Ender-3 V2.

**Disclaimer:** do not blindly use these files for your Marlin build, they are set up for my modded printer and will at best not work on yours.
Only use them as reference for your own customization and don't come blame me if your printer breaks or your house burns down.

Configurations are based on the `config/examples/Creality/Ender-3 V2/CrealityV422/MarlinUI` example.

## My Ender-3 V2 mods

- Stock Creality 4.2.2 Silent mainboard replaced with BIGTREETECH SKR V1.4 and a mix of stepper drivers
- Stock display replaced with standard RepRapDiscount Full Graphic Smart Controller (even though there is now official UI support for the stock DWIN display)
    - TODO: find way to connect original display to SKR board and use new Marlin UI
- Trianglelab 3D Touch (BLTouch clone) with this mount: https://www.thingiverse.com/thing:4462870
- Aluminium extruder assembly
- Capricorn Bowden tube
- Dual Z-axis: additional stepper motor and lead screw

## Configurations

My current configuration: skr14_lv8729extr

BLTouch probe wires (black and white) must be connected in place of the Z endstop instead of the "Probe" header. Black is GND and white is signal.

To build for [BIGTREETECH SKR V1.4](https://github.com/bigtreetech/BIGTREETECH-SKR-V1.3/tree/master/BTT%20SKR%20V1.4/), change in `platformio.ini`:
```ini
default_envs = LPC1768
```

### creality422

Taken from Creality official source code, only for reference.

### skr14_lv8729extr

SKR V1.4 with TMC2208 drivers in UART mode for X Y Z and LV8729 for E0.

[LV8729 module](https://www.aliexpress.com/item/32949865010.html)

    I=Vref/(Rs*5), Rs=0.22Ohm, Imax=1.8A
    Set 0.88V for 800mA
    Pull only MS3 high for 1/16 microstepping

### skr14_manufacturer

Taken from BIGTREETECH official source code, only for reference.

### skr14_tmc2208

SKR V1.4 with TMC2208 drivers in UART mode for X Y Z E0.
