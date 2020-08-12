.. _common-smart-battery-solo:

==================
Solo Smart Battery
==================

The `Solo battery <https://www.amazon.com/3DR-BT11A-Solo-Smart-Battery/dp/B00X97EXEU>`__ is the battery shipped with the 3DR Solo quadcopter. This battery can be supported either on Solo vehicles running Ardupilot or on other Ardupilot-equipped aircraft. 

.. note::

   Support for Solo smart batteries was introduced in Copter-3.3.

.. image:: ../../../images/smart-battery-solo.jpg
    :target: ../_images/smart-battery-solo.jpg

Specifications & Connectivity
=============================

See the `Solo development guide <https://3drobotics.github.io/solodevguide/hardware-batterybay.html>`__ for general specifications, mechanical interface, and connector/pinout information.

SMBus is close enough to I2C that the GND, SDA and SCLK lines from the battery can be connected to the Pixhawk's I2C connector (see I2C pin assignment on :ref:`this page <common-pixhawk-overview_pixhawk_connector_pin_assignments>`).

Setup through Mission Planner
=============================

.. image:: ../../../images/smart-battery-setup-mission-planner.png
    :target: ../_images/smart-battery-setup-mission-planner.png

For the Solo battery, set :ref:`BATT_MONITOR <BATT_MONITOR>` to "5" (which may appear as "SMBus" or "Solo" depending upon the software version).

Restart the board and connect with a ground station and check the battery voltage appears.
The :ref:`BATT_CAPACITY <BATT_CAPACITY>` parameter should be automatically updated to the batteries actual capacity in mAh.

Limitations
===========

-  Battery "address discovery" is not supported so the battery must use the I2C address 0x0B (7 bit address).  Most smart batteries use this address.
-  If using a Solo battery with Copter-3.4.6 (or earlier) with a Pixhawk1, the ArduPilot start-up scripts must be modified to search for the battery on the "external" I2C bus.  This is not necessary if using Copter-3.5 (or higher)
   This can be changed in `the startup scripts <https://github.com/ArduPilot/ardupilot/blob/master/mk/PX4/ROMFS/init.d/rc.APM#L465>`__ (see line below) to tell the **batt_smbus** driver to searching on bus "1" instead of "2":

   ::

       # optional smbus battery monitor
       if batt_smbus -b 2 start 