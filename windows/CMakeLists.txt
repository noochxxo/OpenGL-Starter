cmake_minimum_required(VERSION 3.10)
project(OpenGLStarter)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add GLFW subdirectory
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLFW ${CMAKE_BINARY_DIR}/glfw)

# Add GLAD source file
set(GLAD_SRC ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLAD/src/glad.c)

# Create executable
add_executable(${PROJECT_NAME} 
    src/main.cpp
    ${GLAD_SRC}
)

# Include directories
target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLAD/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLFW/include
    ${CMAKE_CURRENT_SOURCE_DIR}/../dependencies/GLM
)

# Link libraries
# Windows needs opengl32 explicitly
target_link_libraries(${PROJECT_NAME} 
    glfw
    opengl32
)