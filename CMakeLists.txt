cmake_minimum_required(VERSION 2.8)

project(gauss_konrad CXX)

# guard against in-source builds (got this from Eigen)
if(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})
  message(FATAL_ERROR "In-source builds not allowed. Please make a new directory (called a build directory) and run CMake from there. You may need to remove CMakeCache.txt. ")
endif()

#add the customised package searches to the module path
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

# only include tests if requested
if(ENABLE_TESTING)
	add_subdirectory(tests)
endif(ENABLE_TESTING)

add_subdirectory(bench)