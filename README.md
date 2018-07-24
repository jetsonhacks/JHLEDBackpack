# JHLEDBackpack

A library to drive the Adafruit 0.56" 4-Digit 7-Segment Display w/I2C Backpack
from a NVIDIA Jetson Development Kit. Includes a simple example.

http://www.adafruit.com/products/880

To run the example:

First load the prerequisites:

<blockquote>
$ sudo apt-get install libi2c-dev i2c-tools</blockquote>

Then switch over to the JHLEDBackpack/example directory, then:

<blockquote>
$ make
  
$ sudo ./displayExample</blockquote>

By default, the example runs on I2C Bus 1. To change to a different I2C bus (e.g. Bus 0), change displayExample.cpp:

<blockquote>
HT16K33 *displayMatrix = new HT16K33() ;
  
// Add the following line

displayMatrix->kI2CBus = 0; // Use I2C bus 0 

int err = displayMatrix->openHT16K33();</blockquote>

<strong>Note: </strong> You must be able to detect the LED BackPack on the given bus. The default address for the LCD Backpack is 0x70 (this can be changed by soldering jumpers). For example, if the Backpack is wired to Bus 1, you would expect to see 0x70:

<blockquote>
$ sudo i2cdetect -y -r 1
  

0 1 2 3 4 5 6 7 8 9 a b c d e f

00: — — — — — — — — — — — — —

10: — — — — — — — — — — — — — — — —

20: — — — — — — — — — — — — — — — —

30: — — — — — — — — — — — — — — — —

40: — — — — — — — — — — — — — — — —

50: — — — — — — — — — — — — — — — —

60: — — — — — — — — — — — — — — — —

70: 70 — — — — — — —</blockquote>


Running the example, the Display will show a blinking set of dashes, a hexadecimal display, a floating point number display, a count down timer and a clock example. Hit the ‘Esc’ key during the clock example to stop.

<h2>Releases</h2>
<h3>Version 1.1 - July, 2018</h3>
Update Readme with better information

<h3>Version 1.0 - October 2015</h3>
Initial Release

<h2>License</h2>

MIT License

Copyright (c) 2015-2018 JetsonHacks

Copyright (c) 2012  Adafruit Industries

Derived from the Adafruit LED Backpack Library at:

--> https://github.com/adafruit/Adafruit-LED-Backpack-Library

Redistribution code attribution from Adafruit:

  This is a library for our I2C LED Backpacks

  Designed specifically to work with the Adafruit LED Matrix backpacks

  ----> http://www.adafruit.com/products/

  ----> http://www.adafruit.com/products/

  These displays use I2C to communicate, 2 pins are required to
  interface. There are multiple selectable I2C addresses. For backpacks
  with 2 Address Select pins: 0x70, 0x71, 0x72 or 0x73. For backpacks
  with 3 Address Select pins: 0x70 thru 0x77

  Adafruit invests time and resources providing this open source code,
  please support Adafruit and open-source hardware by purchasing
  products from Adafruit!

  Written by Limor Fried/Ladyada for Adafruit Industries.
  MIT license, all text above must be included in any redistribution

