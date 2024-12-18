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
* 24 GPIO, 8 of which are also analog inputs
* Micro SD card socket wired up for SPI interfacing, also has extra pins connected for advanced-user SDIO interfacing (note that there's no released usage code for SDIO in Arduino/Python, so this is a super-cutting-edge setup)
* Onboard RGB NeoPixel
* Onboard #13 LED
* Stemma QT port for I2C peripherals and sensors
* 22-pin 3-lane differential HSTX FPC port with 'Pi 5' compatible pinout
* Reset and Boot buttons on PCB edge
* Pico Probe debug port - 3 pin JST SH compatible
* USB Type C power and data
* 5.5mm / 2.1mm DC jack for 6-12VDC power
* On/off switch for DC jack
* GPIO pin numbers match classic Arduino pins
* RX / TX switch for swapping D0 and D1 locations

You may be wondering about the RX-TX switch: we added this because traditional Arduino board start counting the GPIO for the digital pins with 0-7 and then 8-13. However, the D0/D1 pins are also traditionally the hardware UART Serial1, where D0 is Rx and D1 is Tx. On the RP2350, however, the UART pins are the other around: D0 is Tx and D1 is Rx. Thus a DPDT switch: flip one way to have the GPIO go in order of 0-7, flip the other way to have the logical locations of the hardware UART correct but now the pin order is 1, 0, 2, 3..7. Of course, it's also handy if, like us, you often swap the pins - now you don't need to require or cut/solder traces!

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
