cmake_minimum_required(VERSION 3.10)
project(PhysicsSimulation)

set(CMAKE_CXX_STANDARD 17)

# Include directories
include_directories(include)

# Add GLFW
find_package(glfw3 REQUIRED)
include_directories(${GLFW_INCLUDE_DIRS})

# Add GLM
find_package(glm REQUIRED)
include_directories(${GLM_INCLUDE_DIRS})

# Add source files
set(SOURCES
    src/main.cpp
    src/glad.c
)

add_executable(PhysicsSimulation ${SOURCES})

# Link libraries
target_link_libraries(PhysicsSimulation glfw ${GLFW_LIBRARIES} ${CMAKE_DL_LIBS})
