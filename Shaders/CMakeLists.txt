add_executable(Shaders main.cpp)
target_link_libraries(Shaders glew glfw ${OPENGL_gl_LIBRARY})