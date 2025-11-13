cmake_minimum_required(VERSION 3.10)
project(OpenGLStarter)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add GLFW subdirectory
# This tells CMake to build GLFW from source
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLFW ${CMAKE_BINARY_DIR}/glfw)

# Add GLAD source file
# GLAD is just one .c file we need to compile
set(GLAD_SRC ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLAD/src/glad.c)

# Create executable
add_executable(${PROJECT_NAME} 
    src/main.cpp
    ${GLAD_SRC}
)

# Include directories
# This tells the compiler where to find header files
target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLAD/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLFW/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLM
)

# Link libraries
# This links GLFW and system libraries (X11, pthread, dl for Linux)
target_link_libraries(${PROJECT_NAME} 
    glfw
    ${CMAKE_DL_LIBS}
)