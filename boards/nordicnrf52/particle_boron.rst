..  Copyright (c) 2014-present PlatformIO <contact@platformio.org>
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
       http://www.apache.org/licenses/LICENSE-2.0
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

.. _board_nordicnrf52_particle_boron:

Particle Boron
==============

.. contents::

Hardware
--------

Platform :ref:`platform_nordicnrf52`: The nRF52 Series are built for speed to carry out increasingly complex tasks in the shortest possible time and return to sleep, conserving precious battery power. They have a Cortex-M4F processor which makes them quite capable Bluetooth Smart SoCs.

.. list-table::

  * - **Microcontroller**
    - NRF52840
  * - **Frequency**
    - 64MHz
  * - **Flash**
    - 796KB
  * - **RAM**
    - 243KB
  * - **Vendor**
    - `Particle <https://docs.particle.io/boron?utm_source=platformio.org&utm_medium=docs>`__


Configuration
-------------

Please use ``particle_boron`` ID for :ref:`projectconf_env_board` option in :ref:`projectconf`:

.. code-block:: ini

  [env:particle_boron]
  platform = nordicnrf52
  board = particle_boron

You can override default Particle Boron settings per build environment using
``board_***`` option, where ``***`` is a JSON object path from
board manifest `particle_boron.json <https://github.com/platformio/platform-nordicnrf52/blob/master/boards/particle_boron.json>`_. For example,
``board_build.mcu``, ``board_build.f_cpu``, etc.

.. code-block:: ini

  [env:particle_boron]
  platform = nordicnrf52
  board = particle_boron

  ; change microcontroller
  board_build.mcu = nrf52840

  ; change MCU frequency
  board_build.f_cpu = 64000000L


Uploading
---------
Particle Boron supports the following uploading protocols:

* ``blackmagic``
* ``cmsis-dap``
* ``jlink``
* ``nrfjprog``
* ``nrfutil``

Default protocol is ``nrfutil``

You can change upload protocol using :ref:`projectconf_upload_protocol` option:

.. code-block:: ini

  [env:particle_boron]
  platform = nordicnrf52
  board = particle_boron

  upload_protocol = nrfutil

Debugging
---------

:ref:`piodebug` - "1-click" solution for debugging with a zero configuration.

.. warning::
    You will need to install debug tool drivers depending on your system.
    Please click on compatible debug tool below for the further
    instructions and configuration information.

You can switch between debugging :ref:`debugging_tools` using
:ref:`projectconf_debug_tool` option in :ref:`projectconf`.

Particle Boron does not have on-board debug probe and **IS NOT READY** for debugging. You will need to use/buy one of external probe listed below.

.. list-table::
  :header-rows:  1

  * - Compatible Tools
    - On-board
    - Default
  * - :ref:`debugging_tool_blackmagic`
    - 
    - Yes
  * - :ref:`debugging_tool_cmsis-dap`
    - 
    - 
  * - :ref:`debugging_tool_jlink`
    - 
    - 

Frameworks
----------
.. list-table::
    :header-rows:  1

    * - Name
      - Description

    * - :ref:`framework_zephyr`
      - The Zephyr Project is a scalable real-time operating system (RTOS) supporting multiple hardware architectures, optimized for resource constrained devices, and built with safety and security in mind