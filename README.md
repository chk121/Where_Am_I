# Where_Am_I
This project aims to utilize ROS AMCL package to accurately localize a mobile robot inside a map in the Gazebo simulation environments.
## Set-up
1. If you are working with a native ROS installation or using a VM, some of the following package might need to be installed. You could install them as shown below:
```shell
$ sudo apt-get install ros-kinetic-navigation
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-amcl
```

2. Clone the repository and initialize a workspace 
```shell
git clone https://github.com/chk121/Where_Am_I.git $PATH_TO_PARENT_DIR/Where_Am_I
cd $PATH_TO_PARENT_DIR/Where_Am_I/src
catkin_init_workspace
```

3. Build all packages involved
```shell
cd $PATH_TO_PARENT_DIR/Where_Am_I
catkin_make
```

4. Set-up environment
In every new terminal, it is necessary to
```shell
source devel/setup.bash
```

## Localization: Launching & Testing
First, launch the simulation:
```shell
roslaunch my_robot world.launch
```
In a new terminal, launch the `amcl` launch file:
```shell
roslaunch my_robot amcl.launch
```
Setup your RViz by loading `rviz_config.rviz`.

Now, let's test the performance of the AMCL package! Open another terminal and launch the `teleop` script to control the robot and observe it localize itself in the environment:
```shell
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

## Results
![image](https://github.com/chk121/Where_Am_I/blob/master/Screenshot1.png)
![image](https://github.com/chk121/Where_Am_I/blob/master/Screenshot2.png)
