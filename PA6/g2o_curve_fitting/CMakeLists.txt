cmake_minimum_required(VERSION 3.5.1)

project(code)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_FLAGS "-std=c++11")

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)
set(G2O_ROOT /usr/local/include/g2o)
find_package(G2O REQUIRED)

include_directories("/usr/include/eigen3")

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_DIRS})

add_executable(code main.cpp)

target_link_libraries(code  ${OpenCV_LIBS} g2o_core g2o_stuff)