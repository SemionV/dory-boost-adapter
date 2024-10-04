#Minimized boost dependencies for dory project
#The version of boost used is equal to the version of this project

set(DORY_BUILD_TOOLS_REQUIRED_VERSION 3.18)
cmake_minimum_required(VERSION ${DORY_BUILD_TOOLS_REQUIRED_VERSION})

project(dory-boost-adapter VERSION 1.85.0)

set(TARGET_NAME "boost-dll")
set(TARGET_ALIAS "Boost::dll")

if(DORY_DEPENDENCY_TARGET_NAME)
	set(TARGET_NAME ${DORY_DEPENDENCY_TARGET_NAME})
endif()

if(DORY_DEPENDENCY_TARGET_ALIAS)
	set(TARGET_ALIAS ${DORY_DEPENDENCY_TARGET_ALIAS})
endif()

add_library(${TARGET_NAME} INTERFACE include/boost/dll.hpp)
add_library(${TARGET_NAME} ALIAS ${TARGET_ALIAS})

target_compile_definitions(${TARGET_NAME} INTERFACE BOOST_DLL_USE_STD_FS)

target_include_directories(${TARGET_NAME} INTERFACE include)