cmake_minimum_required(VERSION 3.15)

project(bin2c LANGUAGES C)

add_executable(bin2c src/bin2c.c)

set_property(TARGET bin2c PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
