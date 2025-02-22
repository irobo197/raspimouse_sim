# raspimouse_sim

ROS package suite for Raspberry Pi Mouse Simulator runs on Gazebo

![](https://rt-net.github.io/images/raspberry-pi-mouse/raspimouse_sim_samplemaze_animation.gif)

## ROS Package Status

| main develop<br>(master)|Melodic + Ubuntu Bionic<br>(melodic-devel)|
|:---:|:---:|
|[![industrial_ci](https://github.com/rt-net/raspimouse_sim/workflows/industrial_ci/badge.svg?branch=master)](https://github.com/rt-net/raspimouse_sim/actions?query=branch%3Amaster+workflow%3Aindustrial_ci)|[![industrial_ci](https://github.com/rt-net/raspimouse_sim/workflows/industrial_ci/badge.svg?branch=melodic-devel)](https://github.com/rt-net/raspimouse_sim/actions?query=branch%3Amelodic-devel+workflow%3Aindustrial_ci)|

The follwing branches are not maintained.

* rpim_book_version
* indigo-devel
* kinetic-devel


## Requirements

requires the following to run:

* Ubuntu
  * Ubuntu Bionic Beaver 18.04.*
* ROS
  * ROS Melodic Morenia
* Gazebo
  * Gazebo 9.x
* ROS Package
  * ros-melodic-desktop-full

## Installation

Download this ROS package.

```
cd ~/catkin_ws/src
git clone https://github.com/irobo197/raspimouse_sim.git
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
```

Install the dependent ROS packages.

```
cd ~/catkin_ws/src/raspimouse_sim
rosdep install -r -y -i --from-paths raspimouse*
```

Build this package using `catkin_make`.

```
cd ~/catkin_ws && catkin_make
source ~/catkin_ws/devel/setup.bash
```

## QuickStart

After the installation, run the following commands.

```
roslaunch raspimouse_gazebo raspimouse_with_samplemaze.launch
```

Checkout [this page](https://github.com/rt-net/raspimouse_sim/wiki/quickstart) for details.

## Screenshots

### moving in sample maze

```
roslaunch raspimouse_gazebo raspimouse_with_samplemaze.launch
```

![](https://rt-net.github.io/images/raspberry-pi-mouse/raspimouse_sim_samplemaze.png)

### moving with URG

```
roslaunch raspimouse_gazebo raspimouse_with_gasstand.launch
```

![](https://rt-net.github.io/images/raspberry-pi-mouse/raspimouse_sim_urg.png)

### SLAM

```
# 1st terminal
roslaunch raspimouse_slam raspimouse_slam.launch
# 2nd terminal
roslaunch raspimouse_gazebo keyboard_teleop.launch
```

### Navigation

```
# 1st terminal
roslaunch raspimouse_navigation raspimouse_navigation.launch
```

### Autonomous SLAM
```
roslaunch raspimouse_autoslam autonomous_explorer.launch
# or
roslaunch raspimouse_autoslam autonomous_explorer.launch explorer:=RRT
# or
roslaunch raspimouse_autoslam autonomous_explorer.launch explorer:=BUG_WALLFOLLOW
```

## License

This repository is licensed under the MIT license, see [LICENSE]( ./LICENSE ).  
Unless attributed otherwise, everything in this repository is under the MIT license.

### Acknowledgements

* [CIR-KIT/fourth_robot_pkg]( https://github.com/CIR-KIT/fourth_robot_pkg )
  * author
    * RyodoTanaka
  * maintainer
    * RyodoTanaka
  * BSD ([BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause))
  * See [package.xml](https://github.com/CIR-KIT/fourth_robot_pkg/blob/indigo-devel/fourth_robot_control/package.xml) for details.
* [yujinrobot/kobuki]( https://github.com/yujinrobot/kobuki )
  * authors
    * Daniel Stonier
    * Younghun Ju
    * Jorge Santos Simon
    * Marcus Liebhardt
  * maintainer
    * Daniel Stonier
  * BSD ([BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause))
  * See [package.xml](https://github.com/yujinrobot/kobuki/blob/melodic/kobuki/package.xml) for details。
