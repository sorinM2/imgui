project(imgui)

set(SOURCE_FILES imgui.cpp
                imgui_demo.cpp
                imgui_draw.cpp
                imgui_tables.cpp
                imgui_widgets.cpp
                backends/imgui_impl_glfw.cpp
                backends/imgui_impl_opengl3.cpp
                )
add_library(imgui STATIC ${SOURCE_FILES})

find_package(OpenGL REQUIRED)

target_link_libraries(imgui
    PUBLIC
    glfw
    OpenGL::GL
    dl
    pthread
    X11
    Xi
    Xrandr
)
target_include_directories(imgui PUBLIC ../glfw/include/)

target_include_directories(imgui PUBLIC .)
