# Flags

[![Unix](https://github.com/SapphireSuite/Flags/actions/workflows/test_unix.yml/badge.svg)](https://github.com/SapphireSuite/Flags/actions/workflows/test_unix.yml)
[![Windows](https://github.com/SapphireSuite/Flags/actions/workflows/test_windows.yml/badge.svg)](https://github.com/SapphireSuite/Flags/actions/workflows/test_windows.yml)
[![MacOS](https://github.com/SapphireSuite/Flags/actions/workflows/test_macos.yml/badge.svg)](https://github.com/SapphireSuite/Flags/actions/workflows/test_macos.yml)

Sapphire Suite's C++ Flags library.\
Links to the **official** [documentation](https://SapphireSuite.github.io/Flags/).



# How To Use

### Collection Header
```cpp
#include <SA/Collections/Flags>
```


## CMake
Add the subdirectory to the build tree and link the library to your taget:
```cmake
add_subdirectory(Flags)
target_link_libraries(<target> <link> SA_Flags)
```


## Flags
Declare your enum with **bit-flag values** and call the macro *SA_DEFINE_ENUM_FLAGS* following the declaration.

```cpp
enum class MyEnum
{
	None = 0, // optional

	MyValue1 = 1 << 0,
	MyValue2 = 1 << 1,
	MyValue3 = 1 << 2,

	Max // optional
};

SA_DEFINE_ENUM_FLAGS(MyEnum)

```

Then use the *Flags* struct to handle your bit values and apply operations.
```cpp
Flags<MyEnum> flags = MyEnum::MyValue1 | MyEnum::MyValue2;
flags.IsSet(MyEnum::MyValue1); // true
flags.Add(MyEnum::MyValue3);
flags.Remove(MyEnum::MyValue2);
```
For more examples, see [Flags Unit Tests](https://github.com/SapphireSuite/Flags/blob/main/Tests/UnitTests/FlagsTests.cpp)



# Authors

**Maxime "mrouffet" ROUFFET** - main developer (maximerouffet@gmail.com)
