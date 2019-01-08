cmake_minimum_required (VERSION 3.4)
project (prog LANGUAGES CXX C)

# Compiler configuration
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(glfw3 3.2 REQUIRED)
find_package(OpenGL REQUIRED)

add_executable(prog hello.cpp)

target_include_directories(prog PRIVATE ${OPENGL_INCLUDE_DIR})
target_link_libraries(prog ${OPENGL_gl_LIBRARY} -static)

target_link_libraries(prog glfw3 -static)
