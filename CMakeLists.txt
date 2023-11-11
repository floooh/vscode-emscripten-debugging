# CMakeLists.txt
cmake_minimum_required(VERSION 3.5)
project(hello)
add_executable(hello hello.c)
if (CMAKE_SYSTEM_NAME STREQUAL Emscripten)
    set(CMAKE_EXECUTABLE_SUFFIX .html)
    target_link_options(hello PUBLIC -sUSE_WEBGL2=1 --shell-file=../shell.html)
endif()
