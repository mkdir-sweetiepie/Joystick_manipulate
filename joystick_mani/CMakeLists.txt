cmake_minimum_required(VERSION 3.0.2)
project(joystick_mani)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  sensor_msgs
  message_generation
)

generate_messages(DEPENDENCIES std_msgs)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES joystick_mani
  CATKIN_DEPENDS geometry_msgs roscpp sensor_msgs
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_executable(joystick_mani src/joy_cmd_vel_mani.cpp)
target_link_libraries(joystick_mani ${catkin_LIBRARIES})
