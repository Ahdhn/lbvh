#CMake minimum requirement 
cmake_minimum_required(VERSION 3.19 FATAL_ERROR)

set(exec_name "LBVH")

#Executable
add_executable(${exec_name} main.cu aabb.cuh bvh.cuh morton_code.cuh predicator.cuh query.cuh utility.cuh)

#Libs linked to the executable
target_link_libraries( ${exec_name}	
	$<BUILD_INTERFACE:developer_flags>	
	gtest_main
)

#gtest_discover_tests(${exec_name})
