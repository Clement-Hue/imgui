cmake_minimum_required(VERSION 3.10)
project(Imgui VERSION 1.89)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SOURCES imgui.cpp imgui_demo.cpp imgui_draw.cpp imgui_widgets.cpp
        imgui_tables.cpp backends/imgui_impl_sdl2.cpp backends/imgui_impl_opengl3.cpp)

set(HEADERS imconfig.h imgui.h imgui_internal.h imstb_rectpack.h imstb_textedit.h
        imstb_truetype.h backends/imgui_impl_sdl2.h backends/imgui_impl_opengl3.h)

add_library(imgui-static STATIC ${SOURCES} ${HEADERS})
target_include_directories(imgui-static PUBLIC .)
