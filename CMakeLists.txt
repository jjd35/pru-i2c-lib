
cmake_minimum_required(VERSION 3.22)
set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_SYSTEM_PROCESSOR pru)
set(CMAKE_TRY_COMPILE_TARGET_TYPE   STATIC_LIBRARY)
set(CMAKE_CROSSCOMPILING 1)
set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)
set(CMAKE_C_COMPILER /usr/bin/clpru)
set(CMAKE_LINKER /usr/bin/lnkpru) 
add_compile_definitions(__ARM_PCS_VFP __PRU__)
project(pru_i2c LANGUAGES C)

add_library(${PROJECT_NAME} STATIC pru_i2c_driver.c) 

target_include_directories(${PROJECT_NAME} PRIVATE 
"/usr/include/am335x/"
"/usr/include/pru/"
"/usr/include/armv7/"
"include/"
)

