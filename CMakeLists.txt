#Minimized boost dependencies for dory project
#The version of boost used is equal to the version of this project

set(DORY_BUILD_TOOLS_REQUIRED_VERSION 3.18)
cmake_minimum_required(VERSION ${DORY_BUILD_TOOLS_REQUIRED_VERSION})

project(dory-boost-adapter VERSION 1.85.0)

set(TARGET_PREFIX "")
set(TARGET_ALIAS_PREFIX "")

if(DORY_DEPENDENCY_TARGET_PREFIX)
	set(TARGET_PREFIX ${DORY_DEPENDENCY_TARGET_PREFIX}-)
	set(TARGET_ALIAS_PREFIX ${DORY_DEPENDENCY_TARGET_PREFIX}::)
endif()

add_library(${TARGET_PREFIX}boost-dll INTERFACE include/boost/dll.hpp)
add_library(${TARGET_ALIAS_PREFIX}Boost::dll ALIAS boost-dll)

target_compile_definitions(boost-dll INTERFACE BOOST_DLL_USE_STD_FS)

target_include_directories(boost-dll INTERFACE include)