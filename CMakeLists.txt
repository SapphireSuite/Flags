# Copyright (c) 2022 Sapphire's Suite. All Rights Reserved.

cmake_minimum_required(VERSION 3.16)



# Project

project(SA_Flags)

message("SA_Flags Main directory: ${CMAKE_CURRENT_SOURCE_DIR}")



# Outputs

### Setup output directory
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)		# .exe
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)		# .lib / .a
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)		# .dll / .so



# Library


## Static library.
add_library(SA_Flags INTERFACE)


## Include directories
target_include_directories(SA_Flags INTERFACE Include)


## Compile features

### Standard
target_compile_features(SA_Flags INTERFACE c_std_11)
target_compile_features(SA_Flags INTERFACE cxx_std_20)

### SA_Maths module implementation preprocessor.
target_compile_definitions(SA_Flags INTERFACE SA_FLAGS_IMPL)



# Options

## Add SA_Maths's tests to build tree.
option(SA_FLAGS_BUILD_TESTS_OPT "Should build SA_Maths tests" OFF)



# Entrypoints

add_subdirectory(ThirdParty)

if(SA_FLAGS_BUILD_TESTS_OPT)

	### Enable testing for this directory and below.
	enable_testing()

	add_subdirectory(Tests)
endif()
