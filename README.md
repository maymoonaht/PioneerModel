Pioneer_Model
=============

Slightly further adjusted Pioneer 3-DX model forked from https://github.com/SD-Robot-Vision/PioneerModel
that itself was a slightly adjusted pioneer model that was obtained from https://github.com/RafBerkvens/ua_ros_p3dx

Quick Description
-----------------

From prior README.md file: A ROS/Gazebo Pioneer 3DX model.

Install dependencies: PioneerModel/p3dx_control requires controller_manager to compile

For ROS indigo:
```
$ cd <catkin_ws>/src
$ sudo apt-get install ros-indigo-controller-manager-tests ros-indigo-ros-controllers
$ sudo apt-get install ros-indigo-gazebo-ros-control
```

For ROS jade:
```
$ sudo apt-get install ros-jade-controller-manager-tests ros-jade-ros-controllers
$ sudo apt-get install ros-jade-gazebo-ros-pkgs # Ubuntu 14.04 repository does not include ros-jade-gazebo-ros-control yet...
$ cd <catkin_ws>/src
$ git clone https://github.com/ros-simulation/gazebo_ros_pkgs.git # includes gazebo_ros_control...
$ sudo apt-get install ros-jade-ros-control # for gazebo_ros_control, need transmission_interface
```

Optional installation:
```
$ git clone https://github.com/SD-Robot-Vision/p3dx_mover.git
```

To install this github repository:
```
$ cd <catkin_ws>/src/rss-rse/extern
$ git clone https://github.com/cmcghan/PioneerModel.git
$ cd ../../..
$ catkin_make
```

Testing
-------

Try:
```
0$ roscore
1$ roslaunch p3dx_gazebo_mod gazebo.launch 
```
to show the p3dx rover in a Willow Garage setting.

For keyboard control, install:
```
$ cd <catkin_ws>/src
$ git clone https://github.com/SD-Robot-Vision/p3dx_mover.git
$ cd ..
$ catkin_make
```
then run the 0$ and 1$ commands above in separate terminals and try:
```
2$ rosrun p3dx_mover mover.py 
```
then use the arrow keys to control the robot motion, 'q' to quit.

References:  
http://wiki.lofarolabs.com/index.php/Moving_The_Pioneer_3-DX_In_Gazebo

License
=======

Original license is GPLv3, see LICENSE file in the repository.

Modifications are Copyright (c) 2016, by California Institute of Technology, also under GPLv3.

Modifications were performed by Catharine McGhan.

Modifications include:
- updating README.md file
- changing the package names in all subdirectories to *_mod (for compatibility in case original branch is downloaded)
- removing .project and meow.txt files
- fixing internal naming inside robot model (base_link_*_wheel_joint instead of base_*_wheel_joint)
- adding <hardwareInterface> element to <joint> element inside robot model
- adding default parameters for DiffDrive
- exposing (x,y,z,R,P,Y) parameters (starting position and orientation of p3dx rover) in gazebo.launch

References:  
http://answers.ros.org/question/186681/no-valid-hardware-interface-element-found-in-joint/  
http://answers.ros.org/question/40627/how-do-i-set-the-inital-pose-of-a-robot-in-gazebo/  
http://gazebosim.org/tutorials/?tut=ros_roslaunch

Contact
=======

If you have any questions regarding the contents of this repository, please email Catharine McGhan at <cmcghan@cms.caltech.edu>.

-EOF-
