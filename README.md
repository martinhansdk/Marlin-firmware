# Firmware for my CR-10 with auto bed leveling

Basically TH3D's unified version of Marlin 3D printer firmware plus some configuration for my specific printer. Enables automatic bed leveling with a 5x5 probing grid, tuned the PID hotend and a few other improvements.

# Slicer setup to use automatic bed leveling
In Cura (or any other slicer) add a new Creality3D CR-10 printer, then in the machine settings under **Start G-Code** replace the following:

```
G28 ;Home
```

with this:

```
G28 ;Home
G29 ;Automatic bed leveling
M420 S1 ; Apply bed level mesh
```

# Adjusting the Z probe offset

Print the file `Leveling/Bed level tile.gcode`. This will produce a small 3 cm x 3 cm 1 layer thick tile at the centre of the bed. Compare the resulting tile with the example tiles that I have provided with the printer.

If the nozzle is too close to or too far away from the bed, then adjust the Z-probe offset. This is done directly the printer control box by clicking the knob twice while printing or by finding the option under *Tune*. Any changes you make here take effect immediately, so this can be done while printing. 

**Note:** You need to save the setting to EEPROM with *Control > Store settings* after doing this, otherwise the new setting is lost next time you power off the printer.

## compiling and flashing firmware
To compile and install the firmware again:

  1. Install Arduino IDE
  2. Open `TH3DUF_R2/TH3DUF_R2.ino`
  3. File > Preferences > Additional Boards Manager URLs: insert `https://raw.githubusercontent.com/Lauszus/Sanguino/master/package_lauszus_sanguino_index.json`
  4. In Tools > Boards > Boards Manager install "Sanguino"
  5. Choose Tools > Boards > Sanguino-avr > Sanguino
  6. Choose Tools > Processor: "ATMega1284 or ATMega1284P (16 MHz)"
  7. Connect the CR10 with a USB cable
  8. Select the serial port under Tools > Port
  9. Upload (the arrow in the tool bar)

