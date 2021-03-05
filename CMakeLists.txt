# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# initalize pico_sdk from installed location
# (note this can come from environment, CMake cache etc)

# Pull in Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(pico-ms5837 C CXX ASM)

set(PICO_CXX_ENABLE_EXCEPTIONS 1)

set(PICO_CXX_ENABLE_RTTI 1)

# Initialise the Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(pico-ms5837 main.cpp ms5837.cpp)

pico_set_program_name(pico-ms5837 "pico-ms5837")
pico_set_program_version(pico-ms5837 "0.1")

pico_enable_stdio_uart(pico-ms5837 1)
pico_enable_stdio_usb(pico-ms5837 0)

# Add libraries
target_link_libraries(pico-ms5837 pico_stdlib hardware_i2c)

pico_add_extra_outputs(pico-ms5837)

