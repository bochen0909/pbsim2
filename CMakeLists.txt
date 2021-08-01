cmake_minimum_required(VERSION 3.10)

project(pbsim2 VERSION 0.1.0 LANGUAGES CXX)

#specify the C++ standard
set(CMAKE_STANDARD 14)
set(CMAKE_STANDARD_REQUIRED True)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g3 -ggdb -DDEBUG")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -s")

option(BUILD_TESTS "Build test programs" OFF)
add_custom_target(test)


include_directories("${PROJECT_BINARY_DIR}/src")

add_executable(pbsim src/pbsim.cpp)


