Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-lifx/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/lifx/en/latest/
    :alt: Documentation Status

.. image:: https://img.shields.io/discord/327254708534116352.svg
    :target: https://discord.gg/nBQh6qu
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_lifx/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_lifx
    :alt: Build Status

Control `LIFX devices <https://www.lifx.com>`_ over the internet using CircuitPython.

Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_

You'll also need a library to communicate with an ESP32 as a coprocessor using a WiFiManager object. This library supports connecting an ESP32 using either SPI or UART.

* SPI: `Adafruit CircuitPython ESP32SPI <https://github.com/adafruit/Adafruit_CircuitPython_ESP32SPI>`_

* UART: `Adafruit CircuitPython ESP_ATcontrol <https://github.com/adafruit/Adafruit_CircuitPython_ESP_ATcontrol>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Installing from PyPI
--------------------
On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-lifx/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-lifx

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-lifx

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .env
    source .env/bin/activate
    pip3 install adafruit-circuitpython-lifx

Usage Example
=============

Initialize the LIFX API Client with a WiFiManager object and a
`LIFX Personal Access token <https://cloud.lifx.com/settings>`_:

.. code-block:: python

    lifx = adafruit_lifx.LIFX(wifi, lifx_token)

Set a `LIFX selector <https://api.developer.lifx.com/docs/selectors>`_ label to identify the LIFX device to communicate with.

.. code-block:: python

    lifx_light = 'label:Lamp'

List all connected LIFX devices:

.. code-block:: python

    lights = lifx.list_lights()

Toggle the state of a LIFX device:

.. code-block:: python

    lifx.toggle_light(lifx_light)

Set the brightness of a LIFX device to 50%:

.. code-block:: python

    lifx.set_brightness(lifx_light, 0.5)

Set the color of a LIFX device to blue and the brightness to 100%:

.. code-block:: python

    lifx.set_color(lifx_light, 'on', 'blue', brightness=1.0)

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_lifx/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

Documentation
=============

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
