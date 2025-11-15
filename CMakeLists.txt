cmake_minimum_required(VERSION 3.10)

project (imgui)

add_library(imgui STATIC
	
	# Header Files

	imconfig.h
	imgui.h
	imgui_internal.h
	imstb_rectpack.h
	imstb_textedit.h
	imstb_truetype.h
	imgui_impl_sdl3.h
	imgui_impl_vulkan.h

	
	# Source Files

	imgui.cpp
	imgui_demo.cpp
	imgui_draw.cpp
	imgui_tables.cpp
	imgui_widgets.cpp
	imgui_impl_sdl3.cpp
	imgui_impl_vulkan.cpp
)

target_compile_definitions(imgui PRIVATE IMGUI_IMPL_VULKAN_USE_VOLK)
