cmake_minimum_required(VERSION 3.15)
project(inputGen)

set(CMAKE_CXX_STANDARD 20)
SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -lboost_program_options")
set(CMAKE_CXX_FLAGS "-Wall -Wextra -march=native")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

add_executable(inputGen main.cpp)

find_package(Boost 1.63.0 COMPONENTS program_options)
include_directories(${Boost_INCLUDE_DIRS})
target_link_libraries(inputGen PRIVATE
        tbb
        ${Boost_LIBRARIES})