cmake_minimum_required(VERSION 3.0.0)

project(imgui CXX)

file(GLOB SOURCES "*.cpp" ".c")

add_library(imgui STATIC ${SOURCES})

target_include_directories(imgui PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
