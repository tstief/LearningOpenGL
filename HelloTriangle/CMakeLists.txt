add_executable(HelloTriangle main.cpp)
target_link_libraries(HelloTriangle glew glfw ${GLFW_LIBRARIES})