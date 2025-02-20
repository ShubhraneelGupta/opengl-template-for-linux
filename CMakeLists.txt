cmake_minimum_required(VERSION 3.10)
project(ogl)

set(CMAKE_CXX_STANDARD 17)

include_directories(${PROJECT_SOURCE_DIR}/include)

set(GLFW_DIR ${PROJECT_SOURCE_DIR}/libs/glfw)  # Corrected path
include_directories(${GLFW_DIR}/include)
link_directories(${GLFW_DIR}/lib)

add_executable(ogl src/main.cpp ${PROJECT_SOURCE_DIR}/include/glad/glad.c)

target_link_libraries(ogl ${GLFW_DIR}/lib/libglfw3.a GL dl pthread)
