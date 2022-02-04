---
title: LD06 Lidar
tags: [formatting]
keywords: ROSMower lidar
last_updated: December 12, 2021
summary: "LD06 Lidar instructions"
sidebar: rosmower_Ld06
permalink: ROSMower_Ld06.html
parent: ROSMower Hardware
nav_order: 2
has_children: false
---
## LD06
ROSMower has been equipped with LD06 Lidar, a super small TOF lidar made by ldrobot (inno-maker). The lidar can operate outside and has a detection range up to 12m according
data sheets. I did a first test on sunny conditions with a prototype robot and was satisfied so far [Test outside](https://www.youtube.com/watch?v=kWZzNYni93U).

To mount it on top of PCB box, I changed the PCB box lid  with a special version for LD06. Also a small 3D printed part is used as a mounting block for LD06.
The mounting block is necessary in my opinion because LD06 has one major drawback. It is not fully enclosed, at the bottom, there is a large cutout and PCB of lidar
is not protected. The mounting block improves this (hopefully).

![](/images/ROSMower/LD06.jpg)

First I placed two knurled brass nuts for M2 screws inside the mounting block. To seal the bottom
of lidar, I used 2K silicone which I already used to mold the dampers. To prevent silicone to flow out of the mounting block part during mold process, 
I closed the cutout which routes the cables with some tape. I wanted to ensure no silicone flows into knurled bass nuts. So I blocked them with two toothpicks.
To prevent silicone to flow inside the cable plug of LD06, I again used some tape to close it.

After preparing the silicone, I put it onto the base of mounting block and placed the LD06 on it immediatelly. Now it's time to wait a couple of hours until silicone has been set.
Remove the toothpicks and replace them with M2 screws. Also remove the tape used to protect the cable plug and route the cables into the lidar. 
After everything was finnished, I also put some common 1K silicone into the grove between mounting block and LD06 itself to prevent water entering here.

Before mounting the now LD06 assembly to PCB box lid, I placed a O-Ring 74mm ID, 2mm thickness into the groove at the bottom of mounting block. It acts as sealing
between mounting block and PCB box and will ensure no water enters the PCB box (hopefully)
![](/images/ROSMower/LD06_2.jpg)

