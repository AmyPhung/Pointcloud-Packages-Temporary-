cmake_minimum_required (VERSION 2.8.3)
project (tractor_localization)

find_package (catkin REQUIRED COMPONENTS
  roscpp
  nav_msgs
  geometry_msgs
  tf2_ros
  gps_common
  )

catkin_package (CATKIN_DEPENDS)
include_directories( ${catkin_INCLUDE_DIRS})
