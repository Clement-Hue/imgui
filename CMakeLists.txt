cmake_minimum_required(VERSION 3.20)
project(Imgui VERSION 1.89)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

option(IMGUI_USE_SDL "Build SDL backend" OFF)
option(IMGUI_USE_OPENGL3 "Build Opengl backend" OFF)

set(SOURCES imgui.cpp imgui_demo.cpp imgui_draw.cpp imgui_widgets.cpp
        imgui_tables.cpp)

set(HEADERS imconfig.h imgui.h imgui_internal.h imstb_rectpack.h imstb_textedit.h
        imstb_truetype.h)

if (IMGUI_USE_SDL)
   List(APPEND SOURCES backends/imgui_impl_sdl2.cpp)
   List(APPEND HEADERS backends/imgui_impl_sdl2.h)
endif()
if (IMGUI_USE_OPENGL3)
    List(APPEND SOURCES backends/imgui_impl_opengl3.cpp)
    List(APPEND HEADERS  backends/imgui_impl_opengl3.h)
endif()
add_library(imgui-static STATIC ${SOURCES} ${HEADERS})
target_include_directories(imgui-static PUBLIC .)
if (IMGUI_USE_SDL)
    target_link_libraries(imgui-static PRIVATE SDL2_image::SDL2_image-static)
endif()
