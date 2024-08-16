
cmake_minimum_required(VERSION 3.5.0)

project(imgui CXX)


add_library(imgui SHARED
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp
)


target_include_directories(imgui PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_definitions(imgui PRIVATE "IMGUI_API=__declspec(dllexport)")
