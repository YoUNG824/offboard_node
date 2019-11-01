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
mkdir -p catkin_ws/src
cd catkin_ws
catkin_init_workspace
cd src
git clone https://github.com/mavlink/mavros.git
git clone https://github.com/mavlink/mavlink.git
cd ..
catkin build
```
```
cd ~/src/catkin_ws/src
git clone  https://github.com/YoUNG824/offboard_node.git
cd ..
catkin build
```
## Run
### run pixhawk connection(MAVROS)
``` 
source ~/src/catkin_ws/devel/setup.bash
roslaunch mavros px4.launch fcu_url:="udp://:14540@127.0.0.1:14557"
```
### run pixhawk&gazebo
```
cd ~/src/Firmware
make px4_sitl gazebo_iris
```
### switch pixhawk to offboard mode
```
source ~/src/catkin_ws/devel/setup.bash
rosrun offboard_pkg offboard_node
```
