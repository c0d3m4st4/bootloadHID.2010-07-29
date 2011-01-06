Objective Development bootloadHID
=================================

Get original source code from http://www.obdev.at/products/vusb/bootloadhid.html

BootloadHID is a USB boot loader for AVR microcontrollers. The uploader tool requires no kernel level driver on Windows and can therefore be run without installing any DLLs.

BootloadHID is a USB boot loader for AVR microcontrollers. It can be used on all AVRs with at least 2 kB of boot loader section, e.g. the popular ATMega8. The firmware is flashed into the upper 2 kB of the flash memory and takes control immediately after reset. If a certain hardware condition is met (this condition can be configured, e.g. a jumper), the boot loader waits for data on the USB interface and loads it into the remaining part of the flash memory. If the condition is not met, control is passed to the loaded firmware.

This boot loader is similar to Thomas Fischl’s avrusbboot, except that it is built on top of the HID device class. This implementation is more user friendly on Windows, since no kernel level drivers need to be installed.


Working with the Boot Loader
----------------------------

The boot loader is quite easy to use. Set the jumper (or whatever condition you have configured) for boot loading on the target hardware, connect it to the host computer and (if not bus powered) issue a Reset on the AVR.

The firmware can now be flashed with the "bootloadHID" tool. It accepts only one parameter: an Intel-Hex file containing the code to be loaded.

For a GUI uploader tool on Windows, get the tool from Mario Steiner at http://vusb.wikidot.com/project:hidbootflash

