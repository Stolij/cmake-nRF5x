cmake_minimum_required(VERSION 3.12)

set(NRF_TARGET nrf52)


if (NOT DEFINED ARM_NONE_EABI_TOOLCHAIN_PATH)
	set(ARM_NONE_EABI_TOOLCHAIN_PATH "/usr/local/bin")
endif ()

set(NRF5_SDK_PATH "${CMAKE_CURRENT_LIST_DIR}/../../toolchains/nRF5/nRF5_SDK")
set(NRFJPROG "${CMAKE_CURRENT_LIST_DIR}/../../toolchains/nRF5/nrfjprog/nrfjprog")

set(USE_SOFTDEVICE true) # Enable SoftDevice flash cmake target
set(SD_FAMILY "s132")
set(SD_REVISION "7.0.1")

include("${CMAKE_CURRENT_LIST_DIR}/../CMake_nRF5x.cmake")

nRF5x_toolchainSetup()

project(ExampleProject C)

add_subdirectory(src)