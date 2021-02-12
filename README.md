# Marlin Configurations

[MarlinFirmware/Marlin@bugfix-2.0.x](https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x) configuration files for my modded Creality Ender-3 V2.

**Disclaimer:** do not blindly use these files for your Marlin build, they are set up for my modded printer and will at best not work on yours.
Only use them as reference for your own customization and don't come blame me if your printer breaks or your house burns down.

Configurations are updated to the latest available [MarlinFirmware/Configurations@bugfix-2.0.x](https://github.com/MarlinFirmware/Configurations/tree/bugfix-2.0.x) on the day of the commit, from the `config\examples\Creality\Ender-3 V2` example configuration.

To update an existing git cloned Configurations repository: `git reset --hard origin/bugfix-2.0.x` (could also work with a soft reset)

## My Ender-3 V2 mods

Installed:
- Stock Creality 4.2.2 Silent mainboard replaced with BIGTREETECH SKR V1.4 including TMC2208 modules for all axes (also experimenting with different drivers for the extruder)
- Stock display replaced with standard RepRapDiscount Full Graphic Smart Controller
- Trianglelab 3D Touch (BLTOUCH clone) (TODO: add bracket adapter link)
- Aluminium extruder assembly
- Capricorn Bowden tube

Upcoming:
- Dual Z-axis: additional stepper and lead screw

## Configurations

### creality422

Taken from Creality official source code, only for reference.

### skr14_lv8729extr

[BIGTREETECH SKR V1.4](https://github.com/bigtreetech/BIGTREETECH-SKR-V1.3/tree/master/BTT%20SKR%20V1.4/) with TMC2208 drivers in UART mode for X Y Z axes and LV8729 for E0.

```ini
default_envs = LPC1768
```

[LV8729 module](https://www.aliexpress.com/item/32949865010.html)

    I=Vref/(Rs*5), Rs=0.22Ohm, Imax=1.8A
    Set 0.88V for 800mA
    Pull only MS3 high for 1/16 microstepping

### skr14_manufacturer

Taken from BIGTREETECH official source code, only for reference.

### skr14_tmc2208

[BIGTREETECH SKR V1.4](https://github.com/bigtreetech/BIGTREETECH-SKR-V1.3/tree/master/BTT%20SKR%20V1.4/) with TMC2208 drivers in UART mode for X Y Z E0.

```ini
default_envs = LPC1768
```
