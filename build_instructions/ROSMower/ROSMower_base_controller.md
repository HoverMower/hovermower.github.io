---
title: ROSMower base controller
tags: [formatting]
keywords: ROSMower base controller
last_updated: January 27, 2022
summary: "base controller of ROSMower"
sidebar: rosmower_base_controller
permalink: ROSMower_base_controller.html
parent: ROSMower
nav_order: 3
has_children: false
---
## Base controller
A base controller often gets used in robots controlled by ROS. It is some kind of MCU which acts as bridge between ROS ecosystem (running on PC, Raspberry PI or others) and the hardware itself (motor drivers, sensors).
Same is true for ROSMower. An Arduino Nano acts as base controller and is attached to:
- mow motor driver
- mow motor current sensor
- perimeter sensors
- bumper switches
- power management (measure battery voltage, monitor charging, turn on/off entire robot by disconnecting battery )
- user button (hardware interface)
- three MOSFET or relais switches

Some of these devices runs on 5V or higher, so it is not save to attach to RaspberryPI (or similar) directly. The base controller uses a simple UART interface (over USB) to send sensor data and state as well as to receive some simple commands (toggle switches, control mow motor).

If you're interested in the software of this base controller, please refer to this git repositories:
- ![Arduino Firmware for base controller](https://github.com/HoverMower/hovermower_base_controller)
- ![ROS node for base controller](https://github.com/HoverMower/ros_hovermower_base_controller)

If you plan to use this base controller as well, check file config.h for PIN definition
![](/images/ROSMower/base_controller_hardware.jpg)

## Base controller operation
The base controller is used to monitor battery voltage. It is able to detach the entire robot from battery, if voltage drops below a given threshold. This way, you won't discharge your battery to dead. To do so, base controller uses a MOSFET to connect the battery. During boot up, a PIN (pinBatterySwitch) goes high and closes the circuit of battery. To boot the robot, a simple push button is used to close the circuit manually until base controller takes control.

There is one drawback. Each time a serial connection between Arduino and main MCU gets established, Arduino will reboot. This is true to almost any kind of Arduino. During reboot, the battery will be disconnected for a short period of time. If you run your main MCU (Raspberry PI) from the same battery, it will crash as soon as it opens a serial connection because battery gets disconnected.
To oversome this limitation, you can add a 100uF (or similar) capacitor between Arduino RST and GND PIN. This will disable the reboot but you will also not be able to flash your Arduino anymore. To overcome this as well, I attached the capacitor with some cable and connector to be able to disconnect when needed (for flashing).