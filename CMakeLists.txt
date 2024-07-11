cmake_minimum_required(VERSION 2.8.3)
project(respeaker_ros)

find_package(catkin REQUIRED COMPONENTS
  dynamic_reconfigure
  message_generation
  std_msgs
  geometry_msgs)

add_message_files(
  FILES
  DoaWithTime.msg)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs)

generate_dynamic_reconfigure_options(
  cfg/Respeaker.cfg)

catkin_package(
  CATKIN_DEPENDS message_runtime std_msgs geometry_msgs)


# catkin_install_python(
#   PROGRAMS
#   scripts/respeaker_node.py
#   scripts/speech_to_text.py
#   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

# install(DIRECTORY scripts launch
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
#   USE_SOURCE_PERMISSIONS)
