cmake_minimum_required(VERSION 3.0.2)
project(lis_tal)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
 message_generation
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs
)
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES lis_tal
#  CATKIN_DEPENDS roscpp rospy std_msgs
#  DEPENDS system_lib
)

include_directories(
 include
  ${catkin_INCLUDE_DIRS}
)

 add_executable(talker src/talker.cpp)
 target_link_libraries(talker ${catkin_LIBRARIES})
 add_dependencies(talker lis_tal_generate_messages_cpp)
 
 add_executable(listener1 src/listener1.cpp)
 target_link_libraries(listener1 ${catkin_LIBRARIES})
 add_dependencies(listener1 lis_tal_generate_messages_cpp)

 add_executable(listener2 src/listener2.cpp)
 target_link_libraries(listener2 ${catkin_LIBRARIES})
 add_dependencies(listener2 lis_tal_generate_messages_cpp)



