cmake_minimum_required(VERSION 3.10)
project(criptoAES)

set(CMAKE_CXX_STANDARD 14)


add_library(tiny-AES-c tiny-AES-c/aes.c)

add_subdirectory(tiny-AES-c)

add_executable(criptoAES main.cpp)

target_link_libraries(criptoAES PUBLIC tiny-AES-c)

target_include_directories(criptoAES PUBLIC
        "${PROJECT_BINARY_DIR}"
        "${PROJECT_SOURCE_DIR}/tiny-AES-c"
        )