<<<<<<< HEAD
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
=======
cmake_minimum_required(VERSION 3.0.0)

project(imgui CXX)

file(GLOB SOURCES "*.cpp" ".c")

add_library(imgui STATIC ${SOURCES})

target_include_directories(imgui PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
>>>>>>> 2a0c1d74c8f6e4e67ae81d2713cf8d4f1ff4324b
