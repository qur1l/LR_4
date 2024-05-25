cmake_minimum_required(VERSION 3.4)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(hello_world)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib)

add_library(formatter_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/formatter.cpp)
add_library(formatter_ex_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib/formatter_ex.cpp)

target_link_libraries(formatter_ex_lib formatter_lib)

add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

target_link_libraries(hello_world formatter_ex_lib)
