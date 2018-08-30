Robotic Arm
===========

## Installation 
This will assume you have ROS, Gazebo, Rviz and MoveIt installed on a Ubuntu system. Go to the src directory of the workspace and then clone this repo

  	 git clone https://github.com/ajaygunalan/robotic_arm 

  	 cd ..

  	 catkin_make


## Visualization in RViz

To visualize the model of the robot with a gripper, launch the following:

  ```
  roslaunch iiwa_description display.launch 
  ```

You can then use the sliders to change the joint values and the gripper values.

## Spawn in Gazebo

To spawn the robot launch the following:


  ```
  roslaunch iiwa_description gazebo.launch 
  ```

## Simulate in MoveIt

To simulate the robot in MoveIt launch the following:


  ```
  roslaunch iiwa_moveit_config demo.launch 
  ```

## To Do list

* Write controllers to simulate in gazebo
* Interface Gazebo and MoveIt, so that Motion in MoveIt is reflected in Gazebo
* Study more about the architecture of Gazebo & MoveIt Interface and also on concepts such as ROS control, ROS Parameter Server and Joint Trajectory Control
