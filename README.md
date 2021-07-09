# Use-Turtlebot3-wuth-SLAM-approach-to-create-and-save-a-map
# Download and Install Ubuntu on PC
1-Download the proper Ubuntu 16.04 LTS Desktop image for your PC from the links below.
Ubuntu 16.04 LTS Desktop image (64-bit)
2-Follow the instruction below to install Ubuntu on PC.
Install Ubuntu desktop
# Install ROS 1 on Remote PC
Open the terminal with Ctrl+Alt+T and enter below commands one at a time.
In order to check the details of the easy installation script, please refer to the script file.

$ sudo apt-get update
$ sudo apt-get upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh
$ chmod 755 ./install_ros_kinetic.sh 
$ bash ./install_ros_kinetic.sh
If the above installation fails, please refer to the official ROS1 Kinetic installation guide.
# Install Dependent ROS 1 Packages
$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
 ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
# Install TurtleBot3 Packages

$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3
 
 3. Enter these codes in the terminal to install Simulation packages

||Simulation Install 6. 1. 1.

$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

4. Make sure to Type "$ cd" or make a new terminal after the 3rd step

5. After you are done type in this command in the terminal

$ source ~/catkin_ws/devel/setup.bash
6.In a new terminal Run these commands in the terminal to launch the simulation world.

6. 2. 1. Launch Simulation World

$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

7.In a new terminal Run these commands in the terminal to launch the SLAM Node.

6. 2. 2. "Run SLAM Node"

$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
to run the SLAM Node and see the generated map by the Robot.

8.In a new terminal Run this command to be able to interact and control the robot

6. 2. 3. Run Teleoperation Node

$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
After you run the 2 codes Now you should be able to control the robot using the keys WASDX to roam around the gazebo simulated map.

9. After you are done exploring the map with your robot you should save the map using (Ctrl + Alt + T).
