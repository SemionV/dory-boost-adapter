#Minimized boost dependencies for dory project
#The version of boost used is equal to the version of this project

set(BUILD_TOOLS_REQUIRED_VERSION 3.22)
cmake_minimum_required(VERSION ${BUILD_TOOLS_REQUIRED_VERSION})

project(dory-boost-adapter VERSION 1.85.0)

add_library(boost-dll INTERFACE include/boost/dll.hpp)
add_library(Boost::dll ALIAS boost-dll)

target_include_directories(boost-dll INTERFACE include)