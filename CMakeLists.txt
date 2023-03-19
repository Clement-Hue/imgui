cmake_minimum_required(VERSION 3.10)
project(Imgui VERSION 1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(SOURCES imgui.cpp imgui_demo.cpp imgui_draw.cpp imgui_widgets.cpp
        imgui_tables.cpp)

set(HEADERS imconfig.h imgui.h imgui_internal.h imstb_rectpack.h imstb_textedit.h
        imstb_truetype.h)

add_library(imgui ${SOURCES} ${HEADERS})
