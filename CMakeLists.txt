
set(SOURCES imgui.cpp imgui_demo.cpp imgui_draw.cpp imgui_widgets.cpp
        imgui_tables.cpp)

set(HEADERS imconfig.h imgui.h imgui_internal.h imstb_rectpack.h imstb_textedit.h
        imstb_truetype.h)

add_library(imgui ${SOURCES} ${HEADERS})
