cmake_minimum_required(VERSION 3.6)
project(LearningOpenGL)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})

find_package(OpenGL REQUIRED)

#include(ExternalProject)
set(GLEW_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/glew-2.0.0/include")
set(GLEW_SRC_FILE "${PROJECT_SOURCE_DIR}/glew-2.0.0/src/glew.c")

set(GLFW_INCLUDE_DIR "C:/Users/Stief Home/Documents/glfw/include")

include_directories(${GLEW_INCLUDE_DIR} ${GLFW_INCLUDE_DIR})

#ExternalProject_Add(GLFW
#        GIT_REPOSITORY "https://github.com/glfw/glfw"
#        GIT_TAG "master"
#        SOURCE_DIR "${CMAKE_SOURCE_DIR}/External/GLFW"
#        UPDATE_COMMAND ""
#        PATCH_COMMAND ""
#        TEST_COMMAND ""
#        INSTALL_COMMAND ""
#        CMAKE_ARGS -DCMAKE_LIBRARY_OUTPUT_DIRECTORY=${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE}
#                   -DCMAKE_ARCHIVE_OUTPUT_DIRECTORY=${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE}
#                   -DCMAKE_RUNTIME_OUTPUT_DIRECTORY=${PROJECT_SOURCE_DIR}/bin/${CMAKE_BUILD_TYPE})

#set(SOURCE_FILES main.cpp)
#add_executable(HelloTriangle ${SOURCE_FILES})

add_library(glfw UNKNOWN IMPORTED)
set_property(TARGET glfw PROPERTY IMPORTED_LOCATION ${GLFW_INCLUDE_DIR}/GLFW/libglfw3dll.a)

#target_link_libraries(HelloTriangle ${GLEW_LIBRARIES} ${OPENGL_gl_LIBRARY} glfw)

add_subdirectory(HelloTriangle)
add_subdirectory(Shaders)