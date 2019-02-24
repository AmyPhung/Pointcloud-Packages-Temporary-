# Pointcloud-Packages-Temporary-
Temporary place to keep packages that work together to generate pointclouds

# Usage
Put all packages in /src folder in catkin workspace then use catkin_make

# Dependencies
tractor_sim
gravl 

Things to add to launch file:
roslaunch tractor_sim_gazebo tractor_sim.launch
roslaunch gravl mainstate.launch
roslaunch gravl teleop.launch 
roslaunch sim_odom start_odom.launch 
roslaunch sim_localization bringup.launch
roslaunch laser_to_pcl start.launch
roslaunch tractor_sim_description tractor_sim_rviz_amcl.launch


# To Do
Make separate rviz files
Add everything to github
Fix dependencies
Make appropriate launch files (bringup_min and bringup)
