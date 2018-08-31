Robotic Arm
===========

## Installation 
This will assume you have ROS, Gazebo, Rviz and MoveIt installed on a Ubuntu system. Go to the src directory of the workspace and then clone this repo

  	 git clone https://github.com/ajaygunalan/robotic_arm 

  	 cd ..

  	 catkin_make


## Visualization in RViz

To visualize the model of the robot with a gripper, launch the following:

  ```P
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

* Write controllers to control the individual joint, & arm, in gazebo without using MoveIt.
* Study more about the architecture of Gazebo & MoveIt Interface and also on concepts such as ROS control, ROS Parameter Server and Joint Trajectory Control

## References

1. [Motion Planning for Manipulators by Jeremy Zoss](http://aeswiki.datasys.swri.edu/rositraining/Exercises?action=AttachFile&do=get&target=ROS-I+Basic+Developer%E2%80%99s+Training+-+Session+3.pdf)
2. [https://github.com/RethinkRobotics/sawyer_simulator](https://github.com/RethinkRobotics/sawyer_simulator)
3. [https://github.com/IFL-CAMP/iiwa_stack](https://github.com/IFL-CAMP/iiwa_stack)
4. [https://github.com/kuka-isir/iiwa_description](https://github.com/kuka-isir/iiwa_description)
5. [https://github.com/AS4SR/general_info/wiki/Basic-ROS-MoveIt!-and-Gazebo-Integration](https://github.com/AS4SR/general_info/wiki/Basic-ROS-MoveIt!-and-Gazebo-Integration)
