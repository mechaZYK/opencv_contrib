cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
set(the_description "RGBD algorithms")

find_package(OpenCV 3.0 REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_definitions(-DCVAPI_EXPORTS)
include_directories(.)
aux_source_directory(./src/  rgbd_src)
add_library(rgbd  SHARED ${rgbd_src})
target_link_libraries(rgbd ${OpenCV_LIBS})

