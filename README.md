# Firmware for my CR-10 with auto bed leveling

Basically TH3D's unified version of Marlin 3D printer firmware plus some configuration for my specific printer. Enables automatic bed leveling with a 5x5 probing grid, tuned the PID hotend and a few other improvements.

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

