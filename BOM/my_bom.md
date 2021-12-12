---
title: my Bill of material
tags: [formatting]
keywords: my bom, special bill of material
last_updated: November 07, 2021
summary: "List of additional needed parts"
sidebar: my BOM
permalink: my_bom
nav_order: 2
has_children: false
parent: My HoverMower
---

## My Bill of material
As the BOM, bill of material only contains parts needed to build the HoverMower chassis, this more special BOM contains additional parts I used
to build my version of HoverMower. Please use this only as reference as it higly depends on which kind of electronic and software you plan to use. 
My version will be equipped with ROS (Robot Operating System) as software stack.

## Printed parts

| Part | Quantity | Comments |
|-------|--------|---------|
| LD06 mount | 1 | mounting flange to mount LD06 to PCB Box lid |
| Jetson mount | 1 | mounting plate for NVidia Jetson, should also fit to Raspberry PI |
| PCB Box Jetson | 1 | supersedes common PCB Box (PCB Box simple ) |
| PCB Box lid LD06 Lidar | 1 | supersedes common PCB Box lid, with option to mount LD06 Lidar |


## Nuts, Bolts

| Part | Quantity | Comments |
|-------|--------|---------|
| Knurled brass nut M2, OD .. height 4mmm | 2  | mount LD06 Lidar to LD06 Lidar mount  |
| Cylinder screw M2 x 18 | 2 | mount LD06 Lidar to LD06 Lidar mount | 
| Cylinder screw M4 x 20 | 4 | bolt Lidar mount to PCB lid |

## Others

| Part | Quantity | Comments |
|-------|--------|---------|
| Rubber O-Ring, 74mm ID, 2mm thick | 1 | used as seal between LD06 lidar mount and PCB box lid |

## Electronics
| Part | Quantity | Comments |
| Nvidia Jetson Nano 4GB | 1 | main MCU |
| LD06 Lidar | 1 | TOF Lidar |
| BNO085 | 1 | IMU |
| Intel realsense D435 | 1 | Stereo depth camera |
| Arduino Nano | 1 | MCU for perimeter sensor, bumper sensor, power management and control of mow motor |
| Sound Sensor LM386 | 2 | Amplifier for Perimeter signal |
| Coil 11P Ferrit 150mH | 2 | coil for perimeter amplifier | 
| Ardumower Perimeter sender board & components | 1 | Sender module for perimeter signal. Can be replaced with Arduino Nano and L298N (https://www.marotronics.de/Perimeter-Sender-Board-mit-Platinen-Zubehoer-Rasenroboter-Schleifen-Sender) |
| BLDC driver mow motor | 1 | JKBLD300 JKONG Motors| 
| brushless motor JK57BLS02 | 1 | mow motor JKONG Motors |