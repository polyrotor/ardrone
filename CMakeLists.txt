project(ardrone)
cmake_minimum_required (VERSION 2.6)

SET( EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
SET( LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
SET( CMAKE_C_FLAGS "-O3")
SET( CMAKE_C_COMPILER arm-none-linux-gnueabi-g++ )

add_subdirectory(ardrone)
add_subdirectory(controller)
