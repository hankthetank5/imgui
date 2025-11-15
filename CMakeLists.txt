cmake_minimum_required(VERSION 3.10)
include (FetchContent)

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

FetchContent_Declare(
	SDL3
	GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
	GIT_TAG release-3.2.26
)
FetchContent_MakeAvailable(SDL3)

FetchContent_Declare(
	volk
	GIT_REPOSITORY https://github.com/zeux/volk.git
	GIT_TAG 1.4.304
)
FetchContent_MakeAvailable(volk)

target_link_libraries(imgui PUBLIC
	SDL3::SDL3
	volk
}

target_include_directories(imgui PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR}
)







