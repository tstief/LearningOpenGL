add_executable(HelloTriangle main.cpp)

set_target_properties(HelloTriangle PROPERTIES COMPILE_DEFINITIONS "GLEW_NO_GLU;GLEW_BUILD")
		
target_link_libraries(HelloTriangle glew glfw ${OPENGL_gl_LIBRARY})