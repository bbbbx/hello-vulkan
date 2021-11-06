cmake_minimum_required(VERSION 3.10)

project(vulkan-tutorial)

set(CMAKE_CXX_STANDARD 17)

include_directories(
    /usr/local/include # Include Vulkan
    /opt/homebrew/include # Include GLFW, glm
)

link_directories(
    /usr/local/lib
    /opt/homebrew/lib
)
link_libraries(glfw vulkan)

add_executable(main src/main.cpp)
add_executable(test src/test.cpp)


file(
    COPY
    ${CMAKE_CURRENT_SOURCE_DIR}/src/shaders
    DESTINATION
    ${CMAKE_BINARY_DIR}
)