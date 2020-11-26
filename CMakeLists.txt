cmake_minimum_required(VERSION 2.8.3)
project(incon_msgs)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  std_msgs
  message_generation
)

add_message_files(
  FILES
  PoseStampedArray.msg
  BuildingStep.msg
  ObjectTypeWithPose.msg
)

add_service_files(
  FILES
  add_objects.srv
  remove_objects.srv
  add_building_steps.srv
)

generate_messages(
  DEPENDENCIES
  geometry_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS geometry_msgs std_msgs message_runtime
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
