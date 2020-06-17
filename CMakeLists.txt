cmake_minimum_required(VERSION 3.15)

project(bin2c LANGUAGES C)

add_executable(bin2c src/bin2c.c)
set_property(TARGET bin2c PROPERTY INTERPROCEDURAL_OPTIMIZATION)

if (WIN32)
    target_compile_definitions(bin2c PRIVATE _CRT_SECURE_NO_WARNINGS)
endif()
if (MSVC)
    target_compile_options(bin2c PRIVATE /W4)
    set_property(TARGET bin2c PROPERTY MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")
else()
    target_compile_options(bin2c PRIVATE -Wall)
endif()
