## Adafruit Metro RP2350 PCB

<a href="http://www.adafruit.com/products/6003"><img src="assets/6003.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit Metro RP2350. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/6003

### Description

Choo! Choo! This is the RP2350 Metro Line, making all station stops at "Dual Cortex M33 mountain", "528K RAM round-about" and "16 Megabytes of Flash town". This train is piled high with hardware that complements the Raspberry Pi RP2350 chip to make it an excellent development board for projects that want Arduino-shape-compatibility or just need the extra space and debugging ports.

* RP2350 main chip, 150MHz clock, 3.3V logic
* 16 MB of QSPI flash for program storage
* 37 Available GPIO: 23 on the socket/SPI headers, 12 on HSTX port, and another 2 for USB host. 6 of which are also analog inputs
* Micro SD card socket wired up for SPI interfacing, also has extra pins connected for advanced-user SDIO interfacing (note that there's no code for SDIO in Arduino/Python, so this is a super-cutting-edge setup)
* 5V Buck Converter featuring TPS563201 6~17V DC input and up to 2A output
* Onboard RGB NeoPixel
* Onboard #23 LED
* Stemma QT port for I2C peripherals and sensors
* 22-pin 3-lane differential HSTX FPC port with 'Pi 5' compatible pinout, makes for quick DVI video output. Or, this also provides 12 extra GPIO that can be used for more pins.
* Reset and Boot buttons on PCB edge
* Pico Probe debug port - 3 pin JST SH compatible
* USB Type C power and data
* 5.5mm / 2.1mm DC jack for 6-17VDC power
* On/off switch for DC jack
* RX / TX switch for swapping D0 and D1 locations
* USB Host breakout pads - with controllable 5V power and D+/D- for bitbang USB Host.
* GPIO pin numbers match classic Arduino pins, other than GPIO 12 and 13 as those are needed for HSTX connectivity

You may be wondering about the RX-TX switch: we added this because traditional Arduino board start counting the GPIO for the digital pins with 0-7 and then 8-13. However, the D0/D1 pins are also traditionally the hardware UART Serial1, where D0 is Rx and D1 is Tx. On the RP2350, however, the UART pins are the other around: D0 is Tx and D1 is Rx. Thus a DPDT switch: flip one way to have the GPIO go in order of 0-7, flip the other way to have the logical locations of the hardware UART correct but now the pin order is 1, 0, 2, 3..7. Of course, it's also handy if, like us, you often swap the pins - now you don't need to require or cut/solder traces!

Inside the RP2350 is a 'permanent ROM' USB UF2 bootloader. What that means is when you want to program new firmware, you can hold down the BOOTSEL button while plugging it into USB (or pulling down the RUN/Reset pin to ground) and it will appear as a USB disk drive you can drag the firmware onto. Folks who have been using Adafruit products will find this very familiar - we use the technique on all our native-USB boards. Just note you don't double-click reset instead hold down BOOTSEL during boot to enter the bootloader!

There is great C/C++ support, unofficial (but really good) Arduino support, an official MicroPython port, and a CircuitPython port! We of course recommend CircuitPython because we think it's the easiest way to get started and it has support with most of our drivers, displays, sensors, and more, supported out of the box so you can follow along with our CircuitPython projects and tutorials.

While the RP2350 has lots of onboard RAM, it does not have built-in FLASH memory. Instead, that is provided by the external QSPI flash chip. On this board there is 16 MB, which is shared between the program it's running and any file storage used by MicroPython or CircuitPython. When using C/C++ you get the whole flash memory, if using Python you will have about 14 MB remaining for code, files, images, fonts, etc.

RP2350 Chip features:

* Dual ARM Cortex-M33 with floating point unit or Dual RISC-V @ 150MHz
* 520 kB on-chip SRAM
* 8 kB of one-time-programmable (OTP) memory.
* Support for up to 16MB of off-chip Flash memory via dedicated QSPI bus
* Support for external QSPI PSRAM
* DMA controller, 16 channel, 4 IRQ
* Fully-connected AHB crossbar
* On-chip switched-mode power supply and programmable low-dropout regulator (LDO) to generate core voltage
* Two on-chip PLLs to generate 48 MHz USB and 150MHz core clocks
* Optional boot signing with protected OTP storage
* Hardware SHA-256 accelerator
* Hardware random number generator (TRNG)
* 48 GPIO pins, 8 of which can be used as analog inputs
* Peripherals
	* 2 UARTs
	* 2 SPI controllers
	* 2 I2C controllers
	* 24 PWM channels (compared to 16 on RP2040)
	* USB 1.1 controller and PHY, with host and device support
	* 12 PIO state machines

Please note: The Adafruit Metro RP2350 comes with the A2 version of the RP2350, which is affected by the E9 erratum. This errata affects some uses of GPIO and PIO such as high-impedance inputs and the internal pulldowns. You may need to use 8.2K or smaller resistors if pull-downs are required. At this time, Feb 2025, there is no other version of the RP2350 available - only the A2 version.

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
