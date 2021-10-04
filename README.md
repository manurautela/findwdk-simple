# findwdk-simple
Simple driver using FindWdk for building windows driver with cmake from cmdline.

Refer:

[findwdk](https://github.com/SergiusTheBest/FindWDK)

# Build steps
* launch vcvars64.bat VS2019
>%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"
* mkdir build
* cd build
* cmake -G Ninja ..
* cmake --build . --config Debug --target simple

The same should work for the default without Ninja.

# Folder structure
```
│   .gitignore
│   .gitmodules
│   CMakeLists.txt
│   LICENSE
│   README.md
│
├───build
│       .ninja_deps
│       .ninja_log
│
├───FindWDK
│   │   .appveyor.yml
│   │   .editorconfig
│   │   .gitignore
│   │   LICENSE
│   │   README.md
│   │
│   ├───cmake
│   │       FindWdk.cmake
│   │
│   └───samples
│       │   CMakeLists.txt
│       │
│       ├───KmdfCppDriver
│       │       CMakeLists.txt
│       │       Main.cpp
│       │
│       ├───KmdfCppLib
│       │       CMakeLists.txt
│       │       KmdfCppLib.cpp
│       │       KmdfCppLib.h
│       │
│       ├───MinifilterCppDriver
│       │       CMakeLists.txt
│       │       Main.cpp
│       │
│       ├───WdmCppDriver
│       │       CMakeLists.txt
│       │       Main.cpp
│       │
│       ├───WdmCppLib
│       │       CMakeLists.txt
│       │       WdmCppLib.cpp
│       │       WdmCppLib.h
│       │
│       ├───WdmDriver
│       │       CMakeLists.txt
│       │       Main.c
│       │
│       └───WdmLib
│               CMakeLists.txt
│               WdmLib.c
│               WdmLib.h
│
└───simple
        CMakeLists.txt
        simple.c

```

# Build logs.

```
~\dev\temp\driver\findwdk-simple\build>cmake -G Ninja ..
-- The C compiler identification is MSVC 19.29.30133.0
-- The CXX compiler identification is MSVC 19.29.30133.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.29.30133/bin/Hostx64/x64/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.29.30133/bin/Hostx64/x64/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Found WDK: C:/Program Files (x86)/Windows Kits/10/Include/10.0.19041.0/km/ntddk.h
-- WDK_ROOT: C:/Program Files (x86)/Windows Kits/10
-- WDK_VERSION: 10.0.19041.0
-- Configuring done
-- Generating done
-- Build files have been written to: J:/dev/temp/driver/findwdk-simple/build

~\findwdk-simple\build>cmake --build . --config Debug --target simple
[2/2] Linking C executable simple\simple.sys

~\findwdk-simple\build>esc *.sys
~\findwdk-simple\build\simple\simple.sys

~\findwdk-simple\build>
~\findwdk-simple\build>cd simple

~\findwdk-simple\build\simple>ls
CMakeFiles  cmake_install.cmake  simple.pdb  simple.sys

```
