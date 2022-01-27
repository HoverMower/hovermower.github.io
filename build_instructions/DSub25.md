---
title: D-Sub 25 plugs
tags: [formatting]
keywords: instructions
last_updated: December 12, 2021
summary: "Prepare cable routing betweeb PCB Box and Mower chassis"
sidebar: DSub25
permalink: DSub25.html
parent: PCB Box
grand_parent: Build instructions
nav_order: 7
has_children: false
---
## D-Sub 25 plugs
Two pairs of D-Sub 25 connectors are used to route power and signals between PCB Box and mower chassis. I'm not sure if it is a good decision to use this
kind of connectors, but time will tell us.

Two 3D printed parts are used to keep D-Sub connectors in place. One gets mounted into PCB Box, the other to lower chassis. Again, I use some O-Ring as sealing, which are
- O-Ring 83mm ID, 2mm thickness
- O-Ring 107mm ID, 2mm thickness

Place them into the groove of each plate, use some super glue to fix, if needed.
![](/images/dsub25_cover.jpg)

## D-SUB soldering
Now it is up to you to equip any pin you need with cables and connect everything together. Ensure to match each pin on the corresponding plug and check polarityof each connection. In best case, you will check each single connection with your multimeter to ensure good connection and ensure correct mapping. For power connection (i.e. 5V for Raspberry PI), I higly recommend to use mutliple pins (i.e. 3 pins for 5V, 3 pins for GND). Refer to datasheets for current limits of each pin.
If not done before, you should record your pinout of D-SUB25 connectors for reference.
Use some zip ties and sockets to keep cables in place.

![](/images/dsub_soldered.jpg)
![](/images/dsub_cover_placed.jpg)

