cmake_minimum_required(VERSION 3.10)

project(vulkan-tutorial)

set(CMAKE_CXX_STANDARD 17)

# Include Vulkan
include_directories(/usr/local/include)
# Include GLFW, glm
include_directories(/opt/homebrew/include)

add_executable(main src/main.cpp)
add_executable(test src/test.cpp)

target_link_libraries(
    main
    -L/usr/local/lib
    -L/opt/homebrew/lib
    -lglfw
    -lvulkan
)

target_link_libraries(
    test
    -L/usr/local/lib
    -L/opt/homebrew/lib
    -lglfw
    -lvulkan
)

file(
    COPY
    ${CMAKE_CURRENT_SOURCE_DIR}/src/shaders
    DESTINATION
    ${CMAKE_BINARY_DIR}
)