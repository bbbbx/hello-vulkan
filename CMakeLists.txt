cmake_minimum_required(VERSION 3.10)

project(vulkan-tutorial)

find_package(Vulkan REQUIRED)

set(CMAKE_CXX_STANDARD 17)

include_directories(
    ${Vulkan_INCLUDE_DIR}
    ./include
    ./include/glm
)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)
link_libraries(glfw ${Vulkan_LIBRARY})

add_executable(main src/main.cpp)
add_executable(test src/test.cpp)


file(
    COPY
    ${CMAKE_CURRENT_SOURCE_DIR}/src/shaders
    ${CMAKE_CURRENT_SOURCE_DIR}/src/textures
    ${CMAKE_CURRENT_SOURCE_DIR}/src/models
    DESTINATION
    ${CMAKE_BINARY_DIR}
)