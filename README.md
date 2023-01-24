# Euclidean
Firmware for the Sebsongs Modular **Euclidean** eurorack module sold on [Thonk](https://www.thonk.co.uk/shop/sebsongs-euclidean/).

## Background
This firmware is based on the @TomWhitwell euclidean sequencer project.
(https://github.com/TomWhitwell/Euclidean-sequencer-)
It also utilises the improvements made by @sneak-thief.
(https://github.com/sneak-thief/Tombola_Euclidean_Sequencer)

## Modifying the firmware
The firmware is shared on this github page and anyone is welcome to make modifications for their own use and share it with others.

## Version history
The first version uploaded to this repo is version 1.2. This version has all the features of the original Euclidean module firmware, with the following additions:
- Density can now be zero at all sequence lengths.
- Trigger lengths are now around 10ms on all channels.
- Wake up from sleep with reset switch now available.
- Blink pattern for revision check added. The Arduino on board LED blinks 4 times (50ms ON / 200ms OFF).
- Fixed bug where offset could go out of range and never resolve.
- Fixed bug where sequencer freezed when encoder switches were pressed and hold.

## Prerequisites for uploading firmware to an Arduino Nano board
- Install [Arduino IDE 1.8.19](https://www.arduino.cc/en/software). It should work fine with the latest version 2.XX too, but has not been thorougly tested yet.
- For the Arduino Nano Clones that come with the Thonk kit, a driver for the on board CH340 Serial converter must be installed. [Sparkfun](https://learn.sparkfun.com/tutorials/how-to-install-ch340-drivers/all) has a great guide and available drivers.
- The following libraries must be installed in the Arduino IDE before proceeding (Tools/Manage Libraries):
  - **Encoder** version 1.4.2 by Paul Stoffregen
  - **LedControl** version 1.0.6 by Eberhard Fahle
- Connect the Nano board to an available USB port on your computer with a USB to USB mini cable.

## Uploading the firmware
- Open the .ino file in Arduino IDE.
- Make the following settings in the Tools menu:
  - Board: Arduino Nano
  - Processor: Atmega 328P <sub>(if your module was purchased from Thonk before 2023-01-01)</sub>
  - Processor: Atmega 328P (Old Bootloader) <sub>(if your module was purchased from Thonk in or after 2023-01-01)</sub>
  - Port: Should look something like "dev/cu.usbserial-10"
  - Programmer: USBtinyISP
- Compile the firmware by pressing CMD+R (mac) or CTRL+R (win). The Arduino compiler should say "Done compiling" and return no errors.
- Upload the firmware to the Nano board by pressing CMD+U (mac) or CTRL+U (win). If everything went well, the Arduino IDE will return "Done uploading" and return no errors.
