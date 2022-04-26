# Copyright (c) 2022 Sapphire's Suite. All Rights Reserved.



# Project

project(SA_FlagsProto)



# Executable

## Add executable target.
add_executable(SA_FlagsProto "main.cpp")



# Dependencies

### Add library dependencies.
target_link_libraries(SA_FlagsProto PRIVATE SA_Flags)



# Tests

add_test(NAME CSA_FlagsProto COMMAND SA_FlagsProto)
