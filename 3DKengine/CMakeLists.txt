cmake_minimum_required(VERSION 3.24)
project(3DKengine)

set(CMAKE_CXX_STANDARD 14)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(GRAPHICS_LIBS "${PROJECT_SOURCE_DIR}/dependencies")


add_library(3DKengine SHARED src/libmain.cpp src/libmain.h)

find_package(OpenGL REQUIRED)


target_link_directories(3DKengine PUBLIC
        ${GRAPHICS_LIBS}/GLFW/lib-mingw-w64/
        ${GRAPHICS_LIBS}/GLEW/lib/Release/x64/
)

target_link_libraries(3DKengine PUBLIC
        libglfw3.a
        glew32s.lib
        OpenGL32.lib
        )


target_include_directories(3DKengine PUBLIC
        ${GRAPHICS_LIBS}/GLEW/include
        ${GRAPHICS_LIBS}/GLFW/include
        #"C:/Program Files (x86)/Windows Kits/10/Include/10.0.19041.0/um/gl"
        )


