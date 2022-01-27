---
title: ROSMower perimeter
tags: [formatting]
keywords: ROSMower perimeter
last_updated: January 27, 2022
summary: "perimeter sensor"
sidebar: rosmower_perimeter
permalink: ROSMower_perimeter.html
parent: ROSMower
nav_order: 4
has_children: false
---
## Perimeter sensor
Most commercial lawn mower robots use a perimeter wire (fence) to define the mow area. You need to place a wire around your lawn area so it will result in a loop. The mower will only operate inside this loop. 
A perimeter sender (mostly part of charging station) generate a given signal through the perimeter wire whereas one (or multiple) perimeter receivers are used inside the mower to detect thie signal. This way, the mower can distinct if it operates inside the mow area or if it is outside. 
A high sampling rate is used to ensure robot is always inside the perimeter. If mower leaves the moweing area, it detects this within few microseconds and can rotate of drive backwards to enter the area.

ROSMower is equipped with two perimeter receiver (sensors), one on each side. This way, it can detect if it leaves the mowing area and even more, in which direction it needs to turn to get back in. Perimeter sender and receiver was taken from Ardumower project. For details about how to build a perimeter sender / receiver and how it works, please refer to ![wiki.ardumower.de](www.wiki.ardumower.de), ![Ardumower forum](https://www.ardumower.de) and the shop related to Ardumower ![Marotronics](https://www.marotronics.de). You can purchase a perimeter sender PCB and needed parts for perimeter receiver (Sound Sensor LM386 amplifier board and coil) there. But you can also just use an Arduino Nano and L298 motor driver to build a sender.

ROSMower base controller firmware contains necessary code to detect perimeter wire and report this to ROS. The code has also been taken from Ardumower project (Azurit firmware). All credits of this code parts goes to Ardumower project.
![](/images/ROSMower/Perimeter.jpg)
