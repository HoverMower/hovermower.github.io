---
title: BNO085
tags: [formatting]
keywords: ROSMower IMU
last_updated: September 13, 2023
summary: "BNO085 IMU instructions"
sidebar: rosmower_bno085
permalink: ROSMower_bno085.html
parent: ROSMower Hardware
grand_parent: ROSMower
nav_order: 2
has_children: false
---
## BNO085
ROSMower has been equipped with an Adafruit BNO085 IMU, which comes with some build-in sensor fusion algorithm. By this, we don't need to fuse data by our own.

I mounted the sensor at the rear end of PCB box. It connects to NVidia Jetson or RaspberryPI by I2C interface.
To do so connect the sensor like this

|Sensor Pin| GPIO 40 pin header Jetson/PI4 |
|----------|-------------------------------|
| VCC 3.3V | Pin1, 3.3V                    | 
| SDA      | Pin3, SDA1                    |
| SCL      | Pin5, SCL1                    |
| GND      | Pin9, GND                     |

## I2C hints
you can use ```i2cdetect -y -r 1``` command to find device address. However default address will be 4A.

## Installation instructions
If you use ROS noetic, you can simply install necessary driver provided by adafruit with this command
```sudo pip3 install adafruit-circuitpython-bno08x```

### Additional steps for melodic
If you use ROS Melodic, some additional steps needs to be taken. This is caused by different Python versions between Meldoic and Noetic. First install

```sudo apt-get install python3-catkin-pkg-modules```

Adafruit provides detailled instructions on how to [install circuit python found here]
(https://learn.adafruit.com/circuitpython-libraries-on-linux-and-the-nvidia-jetson-nano/initial-setup)

After that, you need to switch back your python environment to Python 2 using this command
```sudo update-alternatives --config python```

### ROS driver
[ROS driver can be found here](https://github.com/PaddyCube/ros_bno08x)

