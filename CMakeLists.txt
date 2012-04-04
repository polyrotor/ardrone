project(ardrone)
cmake_minimum_required (VERSION 2.6)

SET( EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
SET( LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
SET( CMAKE_CXX_FLAGS "-g")
SET( CMAKE_CXX_FLAGS_DEBUG "-g" )

SET( CMAKE_C_COMPILER arm-elf-gcc-4.6.1 )

add_subdirectory(ardrone)
add_subdirectory(controller)
