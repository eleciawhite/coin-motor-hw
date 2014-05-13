coin-motor-hw (Motor Driver Passthrough)
=============
This repository carries the information for fabricating a board that can drive 
a motor with a MOSFET (and pass through other signals)

Some expository and description can be found here: 
http://www.logicalelegance.com/journey/2014/03/releasing-boards/

The original schematic can be found via DigiKey's SchemeIt (which does not 
have layout capabilities at this time):
http://www.digikey.com/schemeit/#fba

The layout was done by Casey Kikendall. (Thank you!)

Pin out:
1 - motor signal
2 - ground
3 - power
4 - passA (I2C SDA)
5 - passB (I2C SCL)

With the N-Channel MOSFET specified in the BOM, a 5V motor can draw a constant 
~270mA (@25C, 210mA @70C). Pulsing the FET or using a higher voltage can lead 
to higher current throughput.

While the MOSFET can pass 60V on the drain side, it turns on at 2V on the 
gate side. (It can go to 20V on the gate side, though I'm driving it with a 
3.3V low current source GPIO.)

This board was designed to work with a 2.7-3.3 V coin-cell style motor (see 
BOM for link to datasheet). This motor has a start up current of 120mA (max) 
and 90mA normal. A more powerful motor could be used with this board.

The pass through signals are (for my project) used for I2C communication to 
a series of accelerometers. However, the are any signals you want to pass 
through.

