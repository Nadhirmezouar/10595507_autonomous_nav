# Turtlebot2 Simulation using CoppeliaSim 
<br>In this simulation, the turtlebot2 module has been mainly deployed into ROS and is simulated in CoppeliaSim. The robot uses the Gmapping package feature to build a map of its surroundings and localize itself. The robot uses the move_base navigation stack to create a path and control its path towards the final goal using the Dijkstra algorithm as the Global Planner and DWA (Dynamic-Window-Approach) as the Local Planner.
<br>
<br>
<br>Repo: 10595507_autonomous_nav
<br>Module: Science and Technology of Autonomous Vehicles ROCO506Z Coursework
<br>
<br>
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
sudo apt-get install ros-kinetic-gmapping
sudo apt-get install ros-kinetic-move-base ros-kinetic-pointcloud-to-laserscan
sudo apt-get install ros-kinetic-dwa-local-planner

```

## Installation:
<br>Open the folder (10595507_autonomous_nav) it contains a folder named autonomous_nav_wss which is a meta package that contains multiple packages. 
<br>Unzip the folder

<br>first step: catkin_make the package turtlebot_msgs.
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss/turtlebot_msgs/
catkin_make
```
<br>then you need to source the package.
```bash
cd ..
source source_all.bash
```
<br>then repeat the same steps as the one above for each and keep this turtlebot_simulation at the end.
<br>
<br>turtlebot
<br>turtlebot_2dslam
<br>turtlebot_interaction
<br>turtlebot_map_and_nav
<br>
<br>after building and sourcing all above pakcages, we do the same for turtlebot_simulation.
<br> 
<br> then we go to this path ~/autonomous_navigation_wss/turtlebot_simulation/devel/lib
<br> copy the file "libv_repExtRos.so" to CoppeliaSim_Edu_V4_1_0_Ubuntu16_04 main folder

### Verifying Installation
<br> move CoppeliaSim_Edu_V4_1_0_Ubuntu16_04 to a new folder in Home directoy called Programs.
<br> open a terminal and source coppeliamSim to bashrc by copying the below code to bashrc
<br> 
```bash
export COPPELIASIM_ROOT_DIR=~/Programs/CoppeliaSim_Edu_V4_1_0_Ubuntu16_04 
alias coppeliaSim="cd $COPPELIASIM_ROOT_DIR && ./coppeliaSim.sh"
```
<br> the on the terminal run ros
```bash
roscore
```
<br> then in a new terminal, source and run coppeliaSim
```bash
source .bashrc
coppeliaSim
```
<br> to verify that your installation is successful, after launch coppleasim, you should find those lines in the previous termnial
```bash
[CoppeliaSim:loadinfo]   plugin 'ROSInterface': loading...
[CoppeliaSim:loadinfo]   plugin 'ROSInterface': load succeeded.
```
## Running the Turtlebot Simulation Package:
<br>first run roscore
```bash
roscore
```
<br>then launch vrep turtlebot_simulation (Coppeliasim)
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss
source source_all.bash
roslaunch vrep_simulation vrep_simulation.launch
```
<br>in a new terminal,launch turtlebot_rviz (Coppeliasim)
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss
source source_all.bash
roslaunch turtlebot_rviz_launchers turtlebot_rviz.launch
```
### SLAM-Gmapping
<br>if you get into Rviz window, you will see that the turtlebot does not appears, you just need to run the simulation in CoppeliaSim. and choose base_link frame.

<br>then run Gmapping to build a map in new terminal. 
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss
source source_all.bash
roslaunch turtlebot_gmapping turtlebot_gmapping.launch
```
<br>when you switch to Rviz, you will see that the map is start to generate.
<br>if there is no map, then add rviz topic by click on add >> by topic >> /map >> Map.
<br>
<br>You can use telop keyboard to move turtlebot in the simulation and generate the map. 
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss
source source_all.bash
roslaunch turtlebot_teleop keyboard_teleop.launch
```
### Path_Plannig
<br>to launch the global planner, open a new terminal and launch the file. 
```bash
cd ~/10595507_autonomous_nav/autonomous_navigation_wss
source source_all.bash
roslaunch turtlebot_navigation turtlebot_move_base.launch
```
<br>then,by looking at Rviz, we can add new topic as well. 
<br>add >> by topic >> /move_base >> /global_planner.
<br>add >> by topic >> /move_base >> /DWAPlannerROS >>/local_plan.
<br>add >> by topic >> /move_base >> /global_costmap.
<br>add >> by topic >> /move_base >> /local_costmap.

## Deployment:
<br> Videos can be found for each implementation step of Gmapping and Path Planning.
<br>[Path Plannig](Path_planning.mp4)
<br> Video can be found explaining Controller tuning.
<br>[Controller Parameters Tuning](Controller-tuning.mp4)
## Authors:
<br> **Mario Gianni**.Intial Developer
<br> **Nadhir Mezouar**. Implementing Turtlebot Simulation and controller develpment
## Acknowledgments:
<br> Thanks to Dr.Mario Gianni for the great course.
