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

Status
--------
I'm currently testing the Revision "H" boards (available under the 'boards' subdirectory) but I can verify that they do appear to work.

I also updated the SA818 footprint in the Eagle part.  A couple of the pads on the left edge (the end with only 4 pins) didn't fit 100% and I always had to contort the soldering iron to get a decent connection.

I have a very small quantity of the trackers assembled and available right now.  They are scheduled to make their initial debut at [Swaptoberfest](http://swaptoberfest.net/wordpress/) so come see them in action!

If you'd like to get your own leoTracker drop me an e-mail.  I'm also looking for people to help beta test the new boards as well.

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