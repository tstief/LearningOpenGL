add_executable(HelloTriangle main.cpp)
target_link_libraries(HelloTriangle glew glfw ${OPENGL_gl_LIBRARY})