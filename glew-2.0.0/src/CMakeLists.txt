add_library(glew STATIC glew.c)
target_compile_definitions(glew PUBLIC GLEW_NO_GLU GLEW_BUILD)