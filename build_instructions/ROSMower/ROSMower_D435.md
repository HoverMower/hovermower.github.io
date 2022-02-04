---
title: D435 stereo depth camera
tags: [formatting]
keywords: ROSMower D435
last_updated: February 04, 2022
summary: "Installation of Intel RealSense D435 stereo depth camera"
sidebar: rosmower_D435
permalink: ROSMower_D435.html
parent: ROSMower ROS Melodic
nav_order: 6
has_children: false
---
## Intel RealSense D435 stereo depth camera
ROSMower uses a Intel RealSense D435 stereo depth camera for computer vision. Plans are to use this camera for 3d mapping using RTABMAP, maybe visual odometry. Other
things which might be done with this camera are obstacle avoidance, detection of small animals or persons which might be harmed by ROSMower.

Intel provides Debian packages for their cameras as well as ROS wrappers. In general, they work fine but when it comes to NVidia Jetson, things can be complicated.
I had some hard time to get it running. The overall installation was not complicated at first shot, but I noticed that even if all versions match the requirements,
I wasn't able to get a Pointcloud of the surrounding of the robot. This is crucial for RTABMAP.
It tooked a couple of days until I figured out, how to get things running. Special thanks to MartyG-RealSense from Intel RealSense team. He is pretty active on github
trying to solve issues reported by users. [You can find the entire discussion here](https://github.com/IntelRealSense/realsense-ros/issues/1967#issuecomment-1027249574).

First of all, it was necessary to build librealsense from source. I first tried with the latest version but still had no luck. Someone suggested to use V2.43.0 and I tried
this with success. This is the process:
1. download zip archive of librealsense V2.43.0 [from here](https://github.com/IntelRealSense/librealsense/releases/tag/v2.43.0)
2. update your CMAKE to a newer version [as described here](https://github.com/IntelRealSense/librealsense/issues/6980#issuecomment-666858977)
3. unzip the archive, switch to the target folder and create a new folder named "build". Change to this folder
4. Use this command to build the library with CUDA support
```
cmake ../ -DFORCE_RSUSB_BACKEND=ON -DBUILD_PYTHON_BINDINGS:bool=true -DPYTHON_EXECUTABLE=/usr/bin/python3.6 -DCMAKE_BUILD_TYPE=release -DBUILD_EXAMPLES=true -DBUILD_GRAPHICAL_EXAMPLES=true -DBUILD_WITH_CUDA:bool=true
```
5. if above step fails because no CUDA compiler was found, edit the file etc/environment and add this line at the end
```
CUDACXX=/usr/local/cuda-10.2/bin/nvcc
```
and try to compile it again as sudo.
6. after compilation was successfully, type this command
```
make -j4
```
7. now, type
```
sudo make installation
```
8. add following lines to your .bashrc. Check if they aren't already there
```
export PATH=$PATH:~/.local/bin
export PYTHONPATH=$PYTHONPATH:/usr/local/lib
export PYTHONPATH=$PYTHONPATH:/usr/local/lib/python3.6/pyrealsense2
```
9. create udev rules with
```
sudo cp ~/.99-realsense-libusb.rules /etc/udev/rules.d/99-realsense-libusb.rules && sudo udevadm control --reload-rules && udevadm trigger
```
10. try to launch realsense-viewer and see if everything works

To build the ROS wrapper, do these steps:
1. Download zip archive of realsense-ros, version V2.2.23 [from here](https://github.com/IntelRealSense/realsense-ros/archive/refs/tags/2.2.23.zip)
2. extract everything into your catkin_ws
3. navigate to your catkin_ws/src/<path to realsense wrapper> and init catkin workspace with
```
catkin_init_workspace
```
4. navigate to your catkin_ws root folder and type 
```
catkin_make clean
catkin_make -DCATKIN_ENABLE_TESTING=False -DCMAKE_BUILD_TYPE=Release
catkin_make install
```

This was gone without any errors but I still wasn't able to visualize pointcloud in RVIZ. To get this running, I had ro re-flash the camera firmware
with version 5.12.12.100 (Release 5.5, March 2021)

Now I was able to see Pointcloud in RVIZ
