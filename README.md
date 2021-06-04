# Turtlebot2 Simulation using CoppeliaSim 
<br>In this simulation, the turtlebot2 module has been mainly deployed into ROS and is simulated in CoppeliaSim. The robot uses the Gmapping package feature to build a map of its surroundings and localize itself. The robot uses the move_base navigation stack to create a path and control its path towards the final goal using the Dijkstra algorithm as the Global Planner and DWA (Dynamic-Window-Approach) as the Local Planner.
<br>
<br>
<br>Repo: 10595507_autonomous_nav
<br>Module: Science and Technology of Autonomous Vehicles ROCO506Z Coursework
<br>
<br>
## Table of Contents



## Getting Started 
<br> Clone this repository to your Home folder.
<br> It is recommended to place the file in Home folder.
<br>
## Prerequisites
<br>The following packages were used to successfully tested and verified using the following:
<br>[Ubuntu 16.04](https://releases.ubuntu.com/16.04/)
<br>[ROS kinteic Desktop Full](http://wiki.ros.org/kinetic/Installation/Ubuntu)
<br>[CoppeliaSim_Edu_V4_1_0_Ubuntu16_04](https://www.coppeliarobotics.com/previousVersions)
<br>
### The following packages are required:
```bash
sudo apt-get install ros-kinetic-navigation
sudo apt-get install ros-kinetic-move-base ros-kinetic-pointcloud-to-laserscan
sudo apt-get install ros-kinetic-dwa-local-planner
```

## Installation:
<br>
