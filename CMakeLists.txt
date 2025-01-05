# 设置项目名称
project(ImGui)

# 搜索源文件
file(
    GLOB
    source
    CONFIGURE_DEPENDS
    ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp
)

# 创建 ImGui 库
add_library(ImGui SHARED ${source})

# 设置包含路径
target_include_directories(ImGui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# 如果是 Windows 平台，设置导出宏
if (WIN32)
    target_compile_definitions(ImGui PRIVATE IMGUI_API=__declspec\(dllexport\))
endif()

# 查找 Vulkan 和 GLFW 库
find_package(Vulkan REQUIRED)

# 链接 GLFW 库
target_link_libraries(ImGui PUBLIC glfw)

# 添加 GLFW 的依赖目录
target_include_directories(ImGui PUBLIC "${GLFW_SOURCE_DIR}/deps")

# 链接 Vulkan 库
target_link_libraries(ImGui PUBLIC Vulkan::Vulkan)
