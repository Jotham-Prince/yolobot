Mobile Object Detection and Surveillance Robot (YOLOv5, OpenCV, ROS2)
---------------------------------------------------------------------

This repository contains the necessary code and instructions to set up a mobile object detection and surveillance robot in a Gazebo Classic simulation environment. The robot utilizes YOLOv5 as its AI engine for object detection, OpenCV for image processing, and ROS2 Humble as the control system. The robot is operated through teleoperation mode using the teleop_twist_keyboard node in ROS2.

Table of Contents
Introduction
Prerequisites
Installation
Usage
Customization
Troubleshooting
Contributing
License
Introduction
The mobile object detection and surveillance robot is designed to navigate in a Gazebo Classic simulation environment and detect objects using YOLOv5, an efficient real-time object detection algorithm. It also employs OpenCV for image processing and ROS2 for control and communication.

Prerequisites
Before proceeding with the installation, ensure you have the following components set up on your system:

ROS2 Humble: Install ROS2 Humble by following the official installation guide for your platform: [ROS2 Installation Guide](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)
Gazebo Classic: Install Gazebo Classic by following the official installation guide for your platform: [Gazebo Classic Installation Guide](https://classic.gazebosim.org/tutorials?tut=install_ubuntu)
YOLOv5: Install YOLOv5 by following the instructions provided in the official YOLOv5 repository: [YOLOv5 Repository](https://github.com/ultralytics/yolov5)
OpenCV: Install OpenCV by following the instructions provided in the official OpenCV repository: [OpenCV Repository](https://github.com/opencv/opencv)
Installation
Clone this repository to your local machine:
git clone https://github.com/Jotham-Prince/yolobot.git
Navigate to the repository directory:
cd yolobot
Save to grepper
Install the required ROS2 packages:
css
rosdep install --from-paths src --ignore-src --rosdistro <ROS_DISTRO>
Replace <ROS_DISTRO> with the ROS2 distribution you are using (e.g., foxy, galactic, etc.).

Build the ROS2 packages:
create a src directory inside yolobot
Copy file structure and code inside yolobot to the src directory
colcon build
Usage
Follow these steps to run the mobile object detection and surveillance robot in the Gazebo Classic simulation environment:

Launch the Gazebo Classic simulation environment:
go to https://github.com/Jotham-Prince/models/ and clone it into /home/.gazebo/ (Ensure to delete the existing models folder or moerge the cloned one and the existing one)
gazebo
Launch the robot control system (ROS2 Humble):
source /yolobot/install/setup.bash
ros2 launch yolobot_gazebo yolobot_launch.py
Launch the teleop_twist_keyboard node for teleoperation:
source /yolobot/install/setup.bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard -r __ns:=/yolobot
Launch the object detection and surveillance node:
source /yolobot/install/setup.bash
cd yolobot/src/yolobot_recognition/scripts
python3 ros_reconition_yolo.py
Save to grepper
You can now use the teleop_twist_keyboard node to control the robot's movement using the keyboard while the robot performs object detection and surveillance in the Gazebo Classic environment.

Customization
You can modify the YOLOv5 model and its configuration files in the yolov5 directory to suit your specific object detection needs.
Adjust parameters in the ros_recognition_yolo.py file to change the behavior of the robot during surveillance.
Troubleshooting
If you encounter any issues while setting up or running the robot, consider the following steps:

Double-check that all dependencies are correctly installed.
Ensure that the ROS2 workspace is sourced properly using the setup.bash file.
Check the Gazebo Classic and ROS2 logs for any error messages.
Ensure you have the necessary custom environment models inside /home/.gazebo/models that are included in the world file
Contributing
We welcome contributions to improve this project. If you find any issues or have ideas for enhancements, feel free to open a pull request.

License
This project is licensed under the MIT License.

Thank you for using yolobot! If you have any questions or need further assistance, please don't hesitate to contact us. Happy robot experimenting!
