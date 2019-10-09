sudo apt-get install libgps-dev

sudo python setup.py install (in gps_common)

catkin_make -DCATKIN_WHITELIST_PACKAGES="gps_common"

https://answers.ros.org/question/190098/how-to-install-gps-common/

Try git clone https://github.com/ktossell/gps_umd.git instead of just /gps_umd.

Or just do a cheap and dirty way with downloading the zip file, and extracting it to your workspace.

Either way, make sure you go into the root of gps_common package and run rosmake.

../catkin_ws/src/gps_common ---->> rosmake

Then build everything with catkin_make

../catkin_ws/ ---->> catkin_make




sudo apt-get install gpsd









sudo apt-get install libgps-dev

sudo python setup.py install (in gps_common)

catkin_make -DCATKIN_WHITELIST_PACKAGES="gps_common"




Robot Pose ekF

git clone https://github.com/ros-planning/robot_pose_ekf.git

sudo apt install ros-kinetic-navigation

catkin_make

<!-- TODO: Add new packages to dependencies list -->

<!-- $ rosdep install robot_pose_ekf
$ roscd robot_pose_ekf
$ rosmake -->

http://wiki.ros.org/robot_pose_ekf
robot_pose_ekf implements an extended Kalman filter for determining the robot pose.
Subscribed Topics
odom (nav_msgs/Odometry)
2D pose (used by wheel odometry): The 2D pose contains the position and orientation of the robot in the ground plane and the covariance on this pose. The message to send this 2D pose actually represents a 3D pose, but the z, roll and pitch are simply ignored.
imu_data (sensor_msgs/Imu)
3D orientation (used by the IMU): The 3D orientation provides information about the Roll, Pitch and Yaw angles of the robot base frame relative to a world reference frame. The Roll and Pitch angles are interpreted as absolute angles (because an IMU sensor has a gravity reference), and the Yaw angle is interpreted as a relative angle. A covariance matrix specifies the uncertainty on the orientation measurement. The robot pose ekf will not start when it only receives messages on this topic; it also expects messages on either the 'vo' or the 'odom' topic.
vo (nav_msgs/Odometry)
3D pose (used by Visual Odometry): The 3D pose represents the full position and orientation of the robot and the covariance on this pose. When a sensor only measures part of a 3D pose (e.g. the wheel odometry only measures a 2D pose), simply specify a large covariance on the parts of the 3D pose that were not actually measured.
The robot_pose_ekf node does not require all three sensor sources to be available all the time. Each source gives a pose estimate and a covariance. The sources operate at different rates and with different latencies. A source can appear and disappear over time, and the node will automatically detect and use the available sensors.To add your own sensor inputs, check out the Adding a GPS sensor tutorial
