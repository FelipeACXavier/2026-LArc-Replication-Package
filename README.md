# 2026-LArc-Replication-Package

Instructions and the necessary code to replicate the case study of the paper ["Verification-Centered Low-Code for Autonomous Robots"](https://doi.org/10.1145/3786179.3788321)

The experiments were executed in laptop with:

- OS: Ubuntu 24.04
- Kernel: 6.8.0-100-generic
- Arch: x86_64

# Installation steps

1. Clone this repository.
2. Install the docker container provided in the repository, this will install:
  - Ubuntu 22.04
  - ROS 2 Humble
  - Install MAKI
3. 

# Running steps

1. Run MAKI.
2. Open one of the available example files.
3. Run the verification.
4. Run the simulation.
5. To execute the ROS nodes:
  - 5.1. Copy the generated node files to the ROS 2 source folder
  - 5.2. Install the other necessary packages
  - 5.3. Compile the generated package
  - 5.4. Execute the necessary nodes in four different terminals:
    - `ros2 launch turtlebot3_manipulation_moveit_config move_group.launch.py`
    - `ros2 launch turtlebot3_manipulation_gazebo gazebo.launch.py world:=./aruco_world.world use_sim_time:=true`
    - `ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True map:=./turtlebot3_world_map.yaml`
    - `ros2 launch pickanddrop default.launch.py`