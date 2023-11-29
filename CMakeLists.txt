cmake_minimum_required(VERSION 3.15)

#c99
set(CMAKE_C_FLAGS "-std=c99")
set(CMAKE_C_FLAGS  "-lws2_32")
# export CC="C:/MinGW/bin/gcc.exe"
# set (CMAKE_C_COMPILER "C:/MinGW/bin/gcc.exe")
# set the project name
project(hello)

# 将可执行文件输出到指定路径
# set(HOME ..)
# set(EXECUTABLE_OUTPUT_PATH ${HOME}/bin)

# add the executable
file(GLOB_RECURSE SRC ${CMAKE_CURRENT_SOURCE_DIR}/app/*.c)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/bsp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/src)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/cpp_support)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/fs_support)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/game)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/log)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/shell_enhance)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/app/letter_shell/extensions/telnet)

add_executable(hello ${SRC})