### Map my World:

This project aims at Mapping a simulated Environment, by applying the Real-Time Appearance Based Mapping (RTAB-Map) in ROS to perform Simultaneous Localization And Mapping (SLAM). Gazebo was used in building a simulated Robot model. The robot was mounted with Hokuyo laser scanner and RGBD camera to perform Simultaneous Localization And Mapping (SLAM).

A database file which contains the mapped environment was generated. It is can be downloaded [here](https://drive.google.com/file/d/1YI6sTHtyBgL9eTJJtzxJaoPn9hFlGpUH/view?usp=sharing).

## Viewing the above downloaded database:
Execute the following command:
```
$ rtabmap-databaseViewer <PATH_TO_DATABASE_FILE>
```

Then on the window that opens:
1. Say yes to using the database parameters
2. View -> Constraint View
3. View -> Graph View
You should be able to see a 2D map of the environment. To view a 3D map of the environment do the following:
4. Edit -> View 3D map

NOTE: 
Install RTAB-Map using the command:
```
sudo apt-get install ros-kinetic-rtabmap-ros
```

## Environmet Setup:
A virtual machine with all the required softwares installed can be downloaded [here](https://s3-us-west-1.amazonaws.com/udacity-robotics/Virtual+Machines/Lubuntu_071917/RoboVM_V2.1.0.zip).

The project requires Ubuntu 16.04 LTS with [ROS Kinetic](http://wiki.ros.org/kinetic), [Gazebo](http://gazebosim.org/) and [catkin](http://wiki.ros.org/catkin) installed.

Install RTAB-Map using the command:
```
sudo apt-get install ros-kinetic-rtabmap-ros
```

## Runnig the packages:

1. Clone this repository.
2. Navigate to the src folder inside the cloned repo and clone the teleop repo from [here](https://github.com/ros-teleop/teleop_twist_keyboard).
3. Then navigate to the root level directory and execute:
```
$ catkin_make
$ source devel/setup.bash
$ roslaunch my_robot world.launch
```
4. To navigate the robot, open a new terminal and navigate to the root directory of the project and execute:
```
$ source devel/setup.bash
$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```
5. To perform SLAM open another new tab and navigate to the root directory of the project and execute:
```
$ source devel/setup.bash
$ roslaunch my_robot mapping.launch
```

Then, use your keybord to move the robot in the simulated environment, the  RTAB-Map will build the map of your environment. On termintig the terminal used for launching SLAM the map will be saved as "./src/my_robot/launch/rtabmap.db".

TO view the above generated file, instructions are given in "Viewing the above downloaded database" section above.