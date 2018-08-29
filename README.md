Robotic Arm
===========

## Installation 
This will assume you have ROS, Gazebo and Rviz installed on a Ubuntu system. Go to the src directory of the workspace and then clone this repo

  	 git clone https://github.com/ajaygunalan/robotic_arm 

  	 cd ..

  	 catkin_make


## Visualization in RViz

To visualize the model of the robot with a gripper, launch the following:

  ```
  roslaunch cool400_description display.launch 
  ```

You can then use the sliders to change the joint values and the gripper values.

## Simulation in Gazebo

To simulate the robot launch the following:


  ```
  roslaunch cool400_description gazebo.launch 
  ```




