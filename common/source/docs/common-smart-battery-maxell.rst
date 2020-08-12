.. _common-smart-battery-maxell:

====================
Maxell Smart Battery
====================

The Maxell battery is another smart battery supported by Ardupilot.

.. note::

   Maxell battery support arrived in Copter-3.5. We have not yet found a webstore that sells the Maxell smart batteries.

.. image:: ../../../images/smart-battery-maxell.png
    :target: ../_images/smart-battery-maxell.png

Connecting to the Pixhawk
=========================

.. image:: ../../../images/smart-battery-maxell-pixhawk.png
    :target: ../_images/smart-battery-maxell-pixhawk.png

The diagram above shows how to connect the Maxell battery to a Pixhawk.

SMBus is close enough to I2C that the GND, SDA and SCLK lines from the battery can be connected to the Pixhawk's I2C connector (see I2C pin assignment on :ref:`this page <common-pixhawk-overview_pixhawk_connector_pin_assignments>`).

Setup through Mission Planner
=============================

.. image:: ../../../images/smart-battery-setup-mission-planner.png
    :target: ../_images/smart-battery-setup-mission-planner.png

If using the Maxell battery set :ref:`BATT_MONITOR <BATT_MONITOR>` to "7" ("SMBus-Maxell").

Restart the board and connect with a ground station and check the battery voltage appears.

Limitations
===========

-  Battery "address discovery" is not supported so the battery must use the I2C address 0x0B (7 bit address).  Most smart batteries use this address.

Additional information
======================

- `Maxell battery announcement (Japanese only) <https://prtimes.jp/main/html/rd/p/000000006.000019742.html>`__

..  youtube:: eIiOLvGYcDs
    :width: 100%