# Reachy MoveIt config
Integration of the Reachy robot in MoveIt for ROS 1

![Reachy in RViz ROS Noetic](https://raw.githubusercontent.com/aubrune/reachy_moveit_config/master/doc/img/moveit.png)

## Getting started
### Install
1. Install [ROS Noetic](http://wiki.ros.org/noetic/Installation) on top of [Ubuntu 20.04](https://ubuntu.com/download/desktop)
2. Install [MoveIt 1](https://moveit.ros.org/install/)
3. Configure [your ROS environment](wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) so that you can sucessfully compile your ROS workspace (e.g. `~/catkin_ws`) with `catkin_make` command
4. `cd ~/catkin_ws/src && git clone https://github.com/aubrune/reachy_moveit_config`
5. `cd ~/catkin_ws/src && git clone https://github.com/aubrune/reachy_description`
6. `cd ~/catkin_ws && catkin_make`
7. `source ~/catkin_ws/devel/setup.bash`

### Use
Just launch the regular MoveIt demo launch file:
```
roslaunch reachy_moveit_config demo.launch
```

Then pickup a group in the **Query Planning Group** from the **Motion Planning** panel (right arm, left arm or head) and move the blue ball appearing at the tip of the end effector to some goal pose. Then click **Plan and Execute** to plan a trajectory with obstacle avoidance and run it with fake trajectory controllers.

You can also use the regular MoveIt [Python](https://ros-planning.github.io/moveit_tutorials/doc/move_group_python_interface/move_group_python_interface_tutorial.html) or [C++](https://ros-planning.github.io/moveit_tutorials/doc/move_group_interface/move_group_interface_tutorial.html) API.

### Basic, Expressive and Advanced configurations
If you are not using the Advanced Reachy configuration, you may disable parts of the robot, e.g. for the Basic configuration:

```bash
roslaunch reachy_moveit_config demo.launch left_arm:=false head:=false
```
