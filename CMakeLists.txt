cmake_minimum_required(VERSION 3.10)
include (FetchContent)

project (imgui)

add_library(imgui STATIC
	imgui.cpp
	imgui_demo.cpp
	imgui_draw.cpp
	imgui_tables.cpp
	imgui_widgets.cpp
	imgui_impl_sdl3.cpp
	imgui_impl_vulkan.cpp
)

target_compile_definitions(imgui PRIVATE IMGUI_IMPL_VULKAN_USE_VOLK)

find_package(SDL3 REQUIRED)
find_package(volk REQUIRED)

target_link_libraries(imgui PUBLIC
	SDL3::SDL3
	volk
)

target_include_directories(imgui PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR}
)









