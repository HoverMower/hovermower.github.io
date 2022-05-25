---
title: RTK GPS base station
tags: [formatting]
keywords: ROSMower RTK GPS base
last_updated: May 25, 2022
summary: "RTK GPS base station"
sidebar: rosmower_gps_base
permalink: ROSMower_GPSBase.html
parent: ROSMower Hardware
grand_parent: ROSMower
nav_order: 1
has_children: false
---
##  RTK-GPS
My initial plan was to use lidar and visual odometry as source of localization and mapping only. I did a lot of tests with different solutions like
- gmapping
- cartographer and
- rtabmap

In the end, they all worked great inside but had issues outside. Localization was not good but was some kind of ok. When tested on wet lawn,
things get even more worse. All attemps to create a good map and localize the robot on it failed. I think the main reason gets caused by wheel slippage.

It was time to take a new decision how to proceed. While I was looking for a solution, I came across OpenMower project. They use a commercial lawn mower, replace
electronics and equip it with ROS. Moreover, they use RTK-GPS solution. I was already aware of such a solution from Ardumower project but they're expensive. However,
OpenMower found a solution to operate RTK-GPS with less costs by using wifi of onboard computer instead relying on Ardusimple XBee radios.
It is still an expensive solution, but I wanted to try this out.

I purchased a kit from Ardusimple containing a simpleRTK board and a UBlox antenna. First, I tried to get correction data over internet from a free NTRIP caster.
Sadly, the closest one I've found is 75km away from my home which means, it is useless for RTK correction data in my case.

## RTK-GPS base station
This means, I need to operate a RTK-GPS station by my own. I purchased another kit from Ardusimple. The idea behind is to mount this kit to a fixed position
and stream my own correction data to local network. To be able to do so, Ardusimple board is hooked to an OrangePi Zero, which is used to stream to network.

First, OrangePi Zero needs to be flashed with Armbian Linux. Also Ardusimple board needs to be re-configured. This can be done with UBlox u-center software and [this configuration 
file from Ardusimple](https://www.ardusimple.com/wp-content/uploads/2020/11/simpleRTK2B_FW113_PPK_UART1USB_1Hz-00.txt). This is done to activate RAW data stream to USB connection.

Last step is to install [RTK-base from Github](https://github.com/Stefal/rtkbase). After configuration, your RTK-base station is ready to go. 
Don't forget to register your station to rtk2go project to get more public available NTRIP caster. Mine is availabe with mount point name Pelm01

## RTK Base station hardware
So the base station consists out of these few parts
- Ardusimple RTK board
- OrangePi Zero
- USB cables

I printed an enclosure for these parts
![](/images/GPS/GPS_base.jpg)

## GPS Antenna
The GPS antenna of base station can be mounted without additional protection as it is already IP67 rated. To get better signal, it commonly gets mounted on a solid sheed of 
metal. Therefore, I milled a disc with 180mm diameter out of 5mm Aluminium and place the antenna on it. Because I didn't like how it looked (WAF), I printed an enclosure as well.
The antenna gets mounted to my TV satellite antenna on the roof of my house.

![](/images/GPS/GPS1.jpg)
![](/images/GPS/GPS2.jpg)
![](/images/GPS/GPS3.jpg)
