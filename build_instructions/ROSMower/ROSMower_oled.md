---
title: OLED
tags: [formatting]
keywords: ROSMower OLED
last_updated: September 13, 2023
summary: "OLED instructions"
sidebar: rosmower_oled
permalink: ROSMower_oled.html
parent: ROSMower Hardware
grand_parent: ROSMower
nav_order: 2
has_children: false
---
## OLED
HoverMower has been equipped with an OLED display, which is located near the kill switch.
It connects to NVidia Jetson or RaspberryPI by I2C interface.

To do so connect the sensor like this

|Sensor Pin| GPIO 40 pin header Jetson/PI4 |
|----------|-------------------------------|
| VCC 3.3V | Pin17, 3.3V                    | 
| SDA      | Pin27, SDA6                    |
| SCL      | Pin28, SCL6                    |
| GND      | Pin25, GND                     |

## I2C hints
you can use ```i2cdetect -y -r 1``` command to find device address. However default address will be 4A.

## Installation instructions
nothing special needed

