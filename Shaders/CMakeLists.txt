add_executable(Shaders main.cpp)

set_target_properties(Shaders PROPERTIES COMPILE_DEFINITIONS "GLEW_NO_GLU;GLEW_BUILD")

target_link_libraries(Shaders glew glfw ${OPENGL_gl_LIBRARY})