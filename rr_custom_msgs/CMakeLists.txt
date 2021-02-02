cmake_minimum_required(VERSION 3.0.2)
project(rr_custom_msgs)

find_package(catkin REQUIRED
    actionlib_msgs
    message_generation
    geometry_msgs
)

add_message_files(
  DIRECTORY msg

  FILES rr_machine_latency.msg
        StringArray.msg
        TaskWaypoint.msg
        TaskWaypointList.msg
        VescState.msg
        VescStateStamped.msg
        Mode.msg
        Float32Stamped.msg
)

add_service_files(
  DIRECTORY srv
  FILES rr_diagnostics/rr_network_latency.srv
        rr_gazebo/SpawnBox.srv
        rr_gazebo/SpawnBoxRandom.srv
        rr_node_tools/RemoveFile.srv
        rr_node_tools/String.srv
        rr_viz/BuildBT.srv
        SetMode.srv
)

add_action_files(
  DIRECTORY action
  FILES db/ToXPosition.action
        envirobot/Docking.action
        rr_behavior_trees/TreeRequest.action
)

generate_messages(
  DEPENDENCIES actionlib_msgs std_msgs geometry_msgs rr_custom_msgs
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
