.. _common-smart-battery:

===============
Smart Batteries
===============

ArduPilot supports several types of "smart batteries" that communicate using `SMBus <https://en.wikipedia.org/wiki/System_Management_Bus>`__.
While not yet very common, smart batteries are easier to attach and detach from the vehicle and are capable of providing more information on the state of the battery including capacity and individual cell voltages.

Limitations
===========

-  Battery "address discovery" is not supported so the battery must use the I2C address 0x0B (7 bit address).  Most smart batteries use this address.

Additional information
======================

- `SMBus specifications (see ver 1.1, ver 2.0) <http://smbus.org/specs/>`__
