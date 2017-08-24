cmake_minimum_required(VERSION 3.5)

project(Playing)

set (Vulkan_root "./Deps/Vulkan/1.0.57.0/x86_64")
set (Src_root "./Src")
set (EXECUTABLE_OUTPUT_PATH ./bin/${CMAKE_BUILD_TYPE})

file(
    GLOB_RECURSE
    Launcher_src
    ${Src_root}/Launcher/*
)

# INCLUDE DIRECTORIES
include_directories(
    ${Vulkan_root}/include
)

# EXECUTABLES
add_executable(Playing
    ${Launcher_src}
)

# LIBRARIES
target_link_libraries(Playing
    ${Vulkan_root}/lib
)