cmake_minimum_required(VERSION 3.22.1 FATAL_ERROR)

project(BlockHock)
set(CMAKE_CXX_STANDARD 11)

include_directories(include)  # Include directory for header files

file(GLOB_RECURSE BHOCK_SOURCE
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
)
find_package(SDL2 REQUIRED)

add_executable(blockhockexec ${BHOCK_SOURCE})

target_link_libraries(blockhockexec
    SDL2::SDL2
    -lSDL2_image
    -lSDL2_mixer
)