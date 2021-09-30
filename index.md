
## Welcome to HoverMower
HoverMower is a robot lawn mower based on Hoverboard Hardware. 

## Why Hoverboard 
In past years, Hoverboards became popular toys. They are build around two really strong brushless hub motors. Also they are equipped with a STM32 based PCB which acts as motor driver. You will also get a 10S2P Li-Ion battery and charger. As many peopple don't use their boards any more, you will find them in after market for only a few €. I paid 20€ for the Hoverboard which acts as base of this project. You will not be able to beat this price for two strong motors, motor driver and battery. 
As the motors are hub motors, it is incredible easy to mount them on any kind of chassis.

## What you will find here
This project will consists out of different repositories. I tried to build it as general as possible meaning, it is up to you to add hard- and software to your own needs. The main repository contains plans, BOM and instructions for a Chassis build by 3D printer. As software and electronics is currently not finalized and because you might want to use other stuff like me, I will only publish these according to my needs. Please feel free to add what ever you need to your build. For example, if you want to build it based on Ardumower Hardware, it can be achieved by just using the chassis plans and ignore the rest.

## Additional resources 
HoverMower uses a custom Firmware to control motors, which gets flashed to the origin HoverBoard PCB. The firmware uses serial commands to drive motor and send sensor data back. You can hook up any kind of MCU, no matter if it is Arduino, RaspberryPI or NVidia Jetson. The firmware is not part of this project, so please have a look here for any reference or instructions.
[https://github.com/alex-makarov/hoverboard-firmware-hack-FOC](Hoverboard Firmware Hack FOC)

If your robot uses ROS (like I plan to do), you can find additional ROS package to control motors by cmd_vel messages here
[https://github.com/alex-makarov/hoverboard-driver](Hoverboard ROS driver)


## Notes
This project is still under development and far away from complete. So please check for updates regulary.

## DISCLAIMER
This project comes without any warranty. It is still under development and things will change. Also as my build is not complete so far,
files may not fit together as planned. You build at your own risk.