cmake_minimum_required(VERSION 3.10)

project(vulkan-tutorial)

find_package(Vulkan REQUIRED)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_MINSIZEREL "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELWITHDEBINFO "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")

include_directories(
    ${Vulkan_INCLUDE_DIR}
    ./include
    ./include/glm
)

link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)
if(MSVC)
    link_libraries(glfw3)
else()
    link_libraries(glfw)
endif(MSVC)
link_libraries(${Vulkan_LIBRARY})

add_executable(main src/main.cpp)
add_executable(test src/test.cpp)


file(
    COPY
    ${CMAKE_CURRENT_SOURCE_DIR}/shaders
    ${CMAKE_CURRENT_SOURCE_DIR}/textures
    ${CMAKE_CURRENT_SOURCE_DIR}/models
    DESTINATION
    ${CMAKE_BINARY_DIR}
)