cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall -O0")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Ofast")
project(ClassyVoxelizer)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(HEADER_DIR ${PROJECT_SOURCE_DIR}/include)
set(SOURCE_DIR ${PROJECT_SOURCE_DIR}/src)
set(HEADER_FILES ${HEADER_DIR}/MultiClassVoxelGrid.h ${HEADER_DIR}/MultiClassVoxelizer.h)

find_package(Eigen3 REQUIRED)

include_directories(${HEADER_DIR})
include_directories(${EIGEN3_INCLUDE_DIR})

add_executable(classy_voxelizer ${SOURCE_DIR}/main.cpp ${SOURCE_DIR}/MultiClassVoxelizer.cpp ${SOURCE_DIR}/MultiClassVoxelGrid.cpp)