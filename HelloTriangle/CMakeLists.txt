add_executable(HelloTriangle main.cpp  ${GLEW_SRC_FILE})
target_link_libraries(HelloTriangle ${OPENGL_gl_LIBRARY} glfw)