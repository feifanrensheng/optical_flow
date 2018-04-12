cmake_minimum_required( VERSION 2.8 )
project( optical_flow )
 
set( CMAKE_BUILD_TYPE "Debug" )
set( CMAKE_CXX_FLAGS "-std=c++11 -O3" )

# 添加Eigen头文件
include_directories( "/usr/include/eigen3" )

find_package( OpenCV 3.1 REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable( optical_flow optical_flow.cpp )
target_link_libraries( optical_flow ${OpenCV_LIBS} )
