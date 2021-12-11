cmake_minimum_required(VERSION 3.21)
project(ogldemo)

set(CMAKE_CXX_STANDARD 23)

add_subdirectory(glfw)
add_subdirectory(glad)
include_directories(glfw/include)
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)

add_executable(ogldemo main.cpp)
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )
target_link_libraries(ogldemo glfw ${GLFW_LIBRARIES} ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} glad)
