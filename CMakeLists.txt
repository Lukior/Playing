cmake_minimum_required(VERSION 3.5)

project(Playing)

set (CMAKE_CXX_STANDARD 11)

set (Vulkan_root "Deps/Vulkan/1.0.57.0/x86_64")
set (Src_root "Src")
set (EXECUTABLE_OUTPUT_PATH ./bin/${CMAKE_BUILD_TYPE})

file(
    GLOB_RECURSE
    Launcher_src
    ${Src_root}/Launcher/*
)

# FIND PACKAGES
find_package(glfw3 3.2 REQUIRED)

# INCLUDE DIRECTORIES
include_directories(
    ${Vulkan_root}/include
)

# LIB DIRECTORIES
link_directories(
    ${Vulkan_root}/lib
)

# EXECUTABLES
add_executable(Playing
    ${Launcher_src}
)

# LIBRARIES
target_link_libraries(Playing
    vulkan
    glfw
)
add_subdirectory(Src/Launcher/Tests)
