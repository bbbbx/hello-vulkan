# Vulkan Tutorial

## Dependencies

- [Vulkan SDK](https://vulkan.lunarg.com/sdk/home)
- [GLFW](https://www.glfw.org/download.html)
- [GLM](https://github.com/g-truc/glm)

## Install, Build and Run

1. Install GLFW and GLM:
    ```bash
    $ brew install glfw glm
    ```
2. Install [Vulkan SDK](https://vulkan.lunarg.com/doc/sdk/1.2.189.0/mac/getting_started.html) to `/usr/local/lib`.
3. Build:
    ```bash
    $ mkdir build && cd build
    $ cmake ..
    $ make
    ```
4. run:
    ```bash
    $ ./test  # minimal test
    $ ./main
    ```

