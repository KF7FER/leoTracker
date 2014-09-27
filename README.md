leoTracker
==========

Small AVR-based standalone APRS Tracker for [Trackuino](http://www.trackuino.org/)

![leoTracker Front](/img/leoTrackerRevG_FrontSmall.jpg?raw=true)

This board was designed to be fairly inexpensive (BOM is $50 depending upon power source), small (1.25"x2.85"), light (under 17g depending upon configuration), and offer some features typically not available on other trackers.  

A ready to fly leoTracker (sans antenna) often weighs less than the power supply needed for other commercial APRS trackers.

Features include:

- ublox MAX-7/8 GPS w/ chip antenna
- Multiple Power options including boost converter (2xAA operation)
- Atmel (AVR) 32u4 Processor (same as in the Arduino Leonardo - hence the "leo")
- On-board USB for easy firmware updates
- microSD socket for data logging/board configuration
- DS18b20 temperature sensor (and connection for off-board sensor)
- NiceRF SA818 2m radio module (frequency agile; multiple power levels)


The leoTracker ONE
------------------

This is a test version of the leoTracker with an on-board single "AA" battery.  Testing has shown that despite running the SA818 just outside of the published specifications, the leoTracker will function correctly for 11+ hours.  It also has a few changes to support soldering the antenna directly to the PCB to reduce overall payload weight.


Status
--------

I just submitted the Revision "J" boards to fabrication and will post the results here.  The primary changes were a slightly changed footprint for the SA818; I changed the crystal footprint to match the part specified in the BOM (which actually has better low-temperature performance); and I cleaned up the silkscreen for fabrication.

Since those are very minor changes I don't expect any problems but I'll update this as soon as I get the boards back in my hands.


Firmware
--------
The firmware is available at [github.com/KF7FER/trackuino](https://github.com/KF7FER/trackuino). It is modified from the [John Boiles](https://github.com/johnboiles/trackuino) port in order to support the different pin mappings used on the leoTracker (as well as support of additional hardware).  This is, of course, based on EA5HAV's original [Trackuino](https://code.google.com/p/trackuino/)

Changes to the firmware include:

- Support for the ublox MAX-6/7/8 (switch to flight mode; use low power mode when possible)
- Support for the on-board microSD card (still a work in progress)
- Support for the Dallas DS18b20 temperature sensors (two are supported)
- Added support for the NiceRF SA818 radio module


I/O Pin Usage
--------
Here is a document listing I/O pin usage for the different leoTracker versions

![leoTracker BOM](/board/PinDefs.xlsx?raw=true)


Powering the leoTracker
--------

The board may be powered by the following methods:

- Add-on TI TPS61202 Boost converter ([Pololu U1V10F3](http://www.pololu.com/product/2563)) on JP1
- 2xAA Boost converter board (files available w/ leoTracker)
- 3.3v LDO board (this is for vehicle/aircraft use) for 5-20v power sources
- A LiPoly/Solar board is currently under development


Bill of Materials
-----------------

The Bill of Materials is a bit out of date but should be fairly close

![leoTracker BOM](/bom/leoTracker_BOM.xlsx?raw=true)
![2xAA Boost BOM](/bom/leoBoost_BOM.xlsx?raw=true)