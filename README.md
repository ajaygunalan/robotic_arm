Robotic Arm
===========

## Installation 
This will assume you have ROS, Gazebo, Rviz and MoveIt installed on a Ubuntu system. Go to the src directory of the workspace and then clone this repo

  	 git clone https://github.com/ajaygunalan/robotic_arm 

  	 cd ..

  	 catkin_make

     source ./devel/setup.bash


## Visualization in RViz

To visualize the model of the robot with a gripper, launch the following:

  ```P
  roslaunch iiwa_description display.launch 
  ```

You can then use the sliders to change the joint values and the gripper values.

## Spawn in Gazebo 

To spawn the robot in Gazebo, launch the following:


  ```
  roslaunch iiwa_description gazebo.launch 
  ```

## To Control the arm in Gazebo

To control individual joints in position mode, launch the following:

launch the following:


  ```
   roslaunch robotic_arm_control robotic_joint_position_gazebo_control.launch 
  ```

To control individual joints in effort mode, launch the following:

  ```
    roslaunch robotic_arm_control robotic_joint_effort_gazebo_control.launch 
  ``` 

To control the entire arm in trajectroy mode, launch the following::

  ```
    roslaunch robotic_arm_control robotic_arm_gazebo_control.launch 
  ``` 


## Simulate in MoveIt

To simulate the robot in MoveIt launch the following:


  ```
  roslaunch iiwa_moveit_config demo.launch 
  ```

## To Plan in MoveIt and Simulate the trajectroy in  Gazebo

To simulate the robot in MoveIt launch the following:

Open up a terminal, then launch the following:


  ```
  roslaunch iiwa_description gazebo.launch 
  ```

Open up another terminal, then launch the following:


  ```
  roslaunch iiwa_moveit_config iiwa_planning_execution.launch 
  ``` 
  
## To Do list

* Enable effort control for each joints with MoveIt-Gazebo setup.
* Follow these tutorial below:

    1. [ROS Control + Gazebo](http://gazebosim.org/tutorials/?tut=ros_control)

    2. [ROS Communication with Gazebo](http://gazebosim.org/tutorials/?tut=ros_comm)
        
    3. [ROS Plugins for Gazebo](http://gazebosim.org/tutorials/?tut=ros_plugins)
        
    4. [Advanced ROS Integration](http://gazebosim.org/tutorials/?tut=ros_advanced)
        
* Study more about the architecture of Gazebo & MoveIt Interface and also on concepts such as ROS control, ROS Parameter Server and Joint Trajectory Control

## References

1. [Motion Planning for Manipulators by Jeremy Zoss](http://aeswiki.datasys.swri.edu/rositraining/Exercises?action=AttachFile&do=get&target=ROS-I+Basic+Developer%E2%80%99s+Training+-+Session+3.pdf)
2. [https://github.com/RethinkRobotics/sawyer_simulator](https://github.com/RethinkRobotics/sawyer_simulator)
3. [https://github.com/IFL-CAMP/iiwa_stack](https://github.com/IFL-CAMP/iiwa_stack)
4. [https://github.com/kuka-isir/iiwa_description](https://github.com/kuka-isir/iiwa_description)
5. [https://github.com/AS4SR/general_info/wiki/Basic-ROS-MoveIt!-and-Gazebo-Integration](https://github.com/AS4SR/general_info/wiki/Basic-ROS-MoveIt!-and-Gazebo-Integration)
6. [[ROS Q&A] 003 - How to control a Gazebo simulated robot with MoveIt! (UR5) - Tutorial](https://www.youtube.com/watch?v=j6bBxfD_bYs&t=144s)
