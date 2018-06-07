cmake_minimum_required (VERSION 2.8)
project(mv_cameras_ros)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

find_package(catkin REQUIRED)

add_definitions(--std=c++11 -Wno-unknown-pragmas)

include_directories(/opt/mvIMPACT_Acquire)

##########################
# EXECUTABLE AND LIBRARY #
##########################
cs_add_library(${PROJECT_NAME}
  src/BinaryBufferReader.cpp
  src/BinaryBufferWriter.cpp
  src/BinaryReader.cpp
  src/BinaryWriter.cpp
  src/CameraManagerNode.cpp
  src/CameraNode.cpp
  src/Condition.cpp
  src/InvalidOperationException.cpp
  src/IOException.cpp
  src/Mutex.cpp
  src/mv_cameras_node.cpp
  src/Serializable.cpp
  src/Thread.cpp
  src/Threads.cpp
  src/Timer.cpp
  src/Timestamp.cpp
  src/TypeCastException.cpp
)

##########
# GTESTS #
##########

##########
# EXPORT #
##########
cs_install()
cs_export()
