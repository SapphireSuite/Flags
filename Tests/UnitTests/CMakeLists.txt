# Copyright (c) 2022 Sapphire's Suite. All Rights Reserved.



# Project

project(SA_FlagsUT)

SA_FetchGoogleTest()



# Executable

## Inputs

file(GLOB_RECURSE SA_FLAGS_UT_SOURCES "*.cpp")

## Add executable target.
add_executable(SA_FlagsUT ${SA_FLAGS_UT_SOURCES})



# Dependencies

### Add library dependencies.
target_link_libraries(SA_FlagsUT PRIVATE SA_Flags)

### Google test module dependency.
target_link_libraries(SA_FlagsUT PRIVATE gtest)



# Tests

add_test(NAME CSA_FlagsUT COMMAND SA_FlagsUT)
