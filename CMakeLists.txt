cmake_minimum_required(VERSION 3.13)
project(MacPackageTest)

set(CMAKE_CXX_STANDARD 14)

set( CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin )
set( CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin )

add_subdirectory(a)
add_subdirectory(b)
add_subdirectory(src)

