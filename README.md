Robotic Arm
===========

## Installation 
This will assume you have ROS, Gazebo, Rviz and MoveIt installed on a Ubuntu system. Go to the src directory of the workspace and then clone this repo

  	 git clone https://github.com/ajaygunalan/robotic_arm 

  	 cd ..

  	 catkin_make

     source ./devel/setup.bash


## To Visualization in RViz & Gazebo

For Rviz launch the following:

  ```
  roslaunch iiwa_description rviz_spawn.launch
  ```

You can then use the sliders to change the joint values and the gripper values.

For Gazebo launch the following:

  ```
   roslaunch iiwa_description gazebo_spawn.launch 
  ```

## To Control in Gazebo

1. To control individual joints in position mode, launch the following:

  ```
   roslaunch iiwa_controllers gazebo_joint_position.launch 
  ```
And the publish the position value to the desired joint (say joint 1) by:

  ```
   rostopic pub /iiwa/joint1_position_controller/command std_msgs/Float64  -- 10.0
  ```

2. To control individual joints in effort mode, launch the following:

  ```
   roslaunch iiwa_controllers gazebo_effort_position.launch
  ``` 
And the publish the effort value to the desired joint (say joint 1) by:

  ```
   rostopic pub /iiwa/joint1_effort_controller/command std_msgs/Float64  -- 10.0
  ```


3. To control the entire arm trajectory in position mode, launch the following::

  ```
   roslaunch iiwa_controllers gazebo_traj_position.launch  
  ``` 

4. To control the entire arm trajectory in effort mode, launch the following::


  ```
   roslaunch iiwa_controllers gazebo_traj_effort.launch  
  ``` 


## To Plan in MoveIt

To Plan the robot in MoveIt launch the following:


  ```
  roslaunch iiwa_moveit_config demo.launch 
  ```

## To Plan in MoveIt and Simulate the trajectroy in  Gazebo

1. For Position Mode launch the following:

Open up a terminal, then launch the following:


  ```
  roslaunch iiwa_controllers gazebo_traj_position.launch   
  ```

Open up another terminal, then launch the following:


  ```
  roslaunch iiwa_moveit_config iiwa_planning_execution.launch 
  ``` 
  
2. For Effort Mode, launch the following:

Open the file ```\iiwa_moveit_config\config\trajectory_execution.launch.xml'``` change the following line

  ``` 
  <arg name="moveit_controller_manager" default="iiwa7" />
  <include file="$(find iiwa_moveit_config)/launch/$(arg moveit_controller_manager)_moveit_traj_position_controller_manager.launch.xml" />
  ```
into this:

  ``` 
  <arg name="moveit_controller_manager" default="iiwa7" />
  <include file="$(find iiwa_moveit_config)/launch/$(arg moveit_controller_manager)_moveit_traj_effort_controller_manager.launch.xml" />
  ```
then launch, these files:

 ```
  roslaunch iiwa_controllers gazebo_traj_effort.launch   

  roslaunch iiwa_moveit_config iiwa_planning_execution.launch 
  ``` 



## To Do list

* Check why Gazebo-Moveit setup is not working in effort mode ?.
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
