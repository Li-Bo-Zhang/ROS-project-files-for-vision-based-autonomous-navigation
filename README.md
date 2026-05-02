# ROS-project-files-for-vision-based-autonomous-navigation
Multi-attention Guided Convolutional Network for Real-time Unstructured Road Segmentation and Autonomous Navigation in Greenhouse Environments
Startup Commands for Vision-Based Autonomous Navigation Robot
1. Start Robot Chassis
# Enable CAN interface with 500k bitrate for robot chassis
sudo ip link set can0 up type can bitrate 500000
# Launch Bunker robot base driver
roslaunch bunker_bringup bunker_robot_base.launch
2. Start IMU Sensor
# Grant permission to serial port
sudo chmod 777 /dev/ttyUSB0
# Launch IMU data node
rosrun scout_imu scout_imu_node
3. Start LiDAR
# Launch Leishen X10 LiDAR driver
roslaunch lslidar_x10_driver lslidar_x10_serial.launch
4. Start Vision & Navigation Controller
# Activate conda environment for lane detection & visual navigation
conda activate road_line
# Source ROS workspace
source ./devel/setup.bash
# Launch unified robot controller for autonomous navigation
roslaunch robot_control unified_controller.launch
5. Camera
# Launch RealSense depth camera
roslaunch realsense2_camera rs_camera.launch

# Edit USB camera config
sudo gedit /opt/ros/noetic/share/usb_cam/launch/usb_cam-test.launch
