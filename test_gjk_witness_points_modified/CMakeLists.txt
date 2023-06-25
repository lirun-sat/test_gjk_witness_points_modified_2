

cmake_minimum_required(VERSION 3.10)
project(openGJK)

set(CMAKE_C_STANDARD 11)

message("[${CMAKE_PROJECT_NAME}] Welcome, please change user options if needed.")




# INCLUDE LIBRARY AND EXAMPLE DIR
add_subdirectory(lib)
add_subdirectory(example1_c)
