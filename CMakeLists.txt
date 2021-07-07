cmake_minimum_required(VERSION 3.5)
project(FisheyeCorrect)

SET( opencv_HOME /home/tct/opencv_build/ )
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -Ofast" )

include_directories(include/ ${opencv_HOME}/include/ )
link_directories( ${opencv_HOME}/lib)

# 设置要链接的库文件
SET( LIB_PROJECT  opencv_core opencv_highgui opencv_videoio opencv_imgproc opencv_imgcodecs opencv_stitching)

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

file(GLOB CPP_SRC ${PROJECT_SOURCE_DIR}/*.cpp)

add_executable(FisheyeCorrect ${CPP_SRC})
target_link_libraries(FisheyeCorrect ${LIB_PROJECT})