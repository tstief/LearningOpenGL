cmake_minimum_required(VERSION 3.2)
project(LearningOpenGL)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})

find_package(OpenGL REQUIRED)

set(GLEW_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/glew-2.0.0/include)
set(GLFW_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/glfw/include)

include_directories(${GLEW_INCLUDE_DIR} ${GLFW_INCLUDE_DIR})

#add_definitions(-DGLEW_NO_GLU)
#add_definitions(-DGLEW_BUILD)
set (CMAKE_SHARED_LINKER_FLAGS "-nostdlib")

set(GLFW_INSTALL OFF CACHE STRING "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE STRING "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE STRING "" FORCE)

add_subdirectory(glew-2.0.0/src)
add_subdirectory(glfw)
add_subdirectory(HelloTriangle)
add_subdirectory(Shaders)