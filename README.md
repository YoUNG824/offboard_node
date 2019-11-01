# It's a C++ version
## Introduction
Create an offboard node in ros to switch px4 to offboard mode


## Properation
```
cd $HOME
mkdir src
```
```
cd ~/src
git clone https://github.com/PX4/Firmware.git
cd Firmware
make px4_fmu-v4_default
```
```
cd ~/src
mkdir -p catkin_ws
cd catkin_ws
catkin_init_workspace
cd src
git clone https://github.com/mavlink/mavros.git
git clone https://github.com/mavlink/mavlink.git
cd ..
catkin build
```
```
cd ~/src
git clone https://github.com/YoUNG824/offboard_node.git
cd offboard_node
catkin build
```
