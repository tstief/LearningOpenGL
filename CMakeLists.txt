cmake_minimum_required(VERSION 3.6)
project(LearningOpenGL)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})

find_package(OpenGL REQUIRED)

set(GLEW_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/glew-2.0.0/include")
set(GLEW_SRC_DIR "${PROJECT_SOURCE_DIR}/glew-2.0.0/src")
set(GLEW_SRC_FILE "${PROJECT_SOURCE_DIR}/glew-2.0.0/src/glew.c")

include_directories(${GLEW_INCLUDE_DIR} ${GLEW_SRC_DIR} ${PROJECT_SOURCE_DIR}/glfw/include)

set(GLFW_INSTALL OFF CACHE STRING "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE STRING "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE STRING "" FORCE)

add_subdirectory(glew-2.0.0/src)
add_subdirectory(glfw)
add_subdirectory(HelloTriangle)
add_subdirectory(Shaders)