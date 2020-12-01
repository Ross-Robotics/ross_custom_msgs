cmake_minimum_required(VERSION 3.0.2)
project(rr_custom_msgs)

find_package(catkin REQUIRED
    actionlib_msgs
    message_generation
    geometry_msgs
)

add_message_files(
  DIRECTORY msg
)

add_service_files(
  DIRECTORY srv
)

add_action_files(
  DIRECTORY action
)

generate_messages(
  DEPENDENCIES actionlib_msgs std_msgs geometry_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES rr_custom_msgs
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

include_directories(
# include
# ${catkin_INCLUDE_DIRS}
)
