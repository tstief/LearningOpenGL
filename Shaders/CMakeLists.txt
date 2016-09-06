add_executable(Shaders main.cpp ${GLEW_SRC_FILE})
target_link_libraries(Shaders ${OPENGL_gl_LIBRARY} glfw)