cmake_minimum_required(VERSION 2.8.3)
project(display)


find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  sensor_msgs
  std_msgs
)

#generate_messages(DEPENDENCIES sensor_msgs)
catkin_package()
include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(my_subs src/my_subs.cpp)
target_link_libraries(my_subs ${catkin_LIBRARIES})
add_dependencies(my_subs display_generate_messages_cpp)
