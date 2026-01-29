# Install latest CMake

```bash
cd ext/download
wget https://github.com/Kitware/CMake/releases/download/v4.2.3/cmake-4.2.3-linux-x86_64.tar.gz
tar xf cmake-4.2.3-linux-x86_64.tar.gz
cmake-4.2.3-linux-x86_64/bin/cmake --version

man -M cmake-4.2.3-linux-x86_64/man cmake
man cmake-4.2.3-linux-x86_64/man/man7/cmake-buildsystem.7

export PATH=$PWD/cmake-4.2.3-linux-x86_64/bin:$PATH
```

```bash
source bin/init.bash # in the workspace root
```

## Install toolchain

### gcc
```bash
sudo apt-get install build-essential

sudo apt-get install crossbuild-essential-arm64

wget https://developer.arm.com/-/media/Files/downloads/gnu/15.2.rel1/binrel/arm-gnu-toolchain-15.2.rel1-x86_64-aarch64-none-linux-gnu.tar.xz
```

### clang
```bash
sudo apt-get install clang libc++-dev libc++abi-dev

wget https://github.com/llvm/llvm-project/releases/download/llvmorg-21.1.8/LLVM-21.1.8-Linux-X64.tar.xz

wget https://github.com/llvm/llvm-project/releases/download/llvmorg-21.1.8/LLVM-21.1.8-Linux-ARM64.tar.xz
```

### ninja
```bash
sudo apt-get install ninja-build
```

# Toolchain file

```bash
cmake -S . -B out -DCMAKE_TOOLCHAIN_FILE=cmake/toolchain-gcc-x86_64.cmake

LD_LIBRARY_PATH=/usr/aarch64-linux-gnu/lib /usr/aarch64-linux-gnu/lib/ld-linux-aarch64.so.1 out/foo
QEMU_LD_PREFIX=/usr/aarch64-linux-gnu out/foo

# cmake version 4.2.3
cmake -S . -B out --toolchain cmake/toolchain-gcc-x86_64.cmake
```

# Preset

```bash
# cmake version 4.2.3
cmake --list-presets
cmake --list-presets configure
cmake --list-presets build

cmake --preset default
cmake --build --preset default
```

# Dependency

## find_package()
```
set(FOO_ROOT "path containing lib/cmake/Foo") # or FOO_DIR
find_package(Foo REQUIRED) # or in ${CMAKE_PREFIX_PATH}
```

### Search config mode
```
FooConfig.cmake
foo-config.cmake
FooConfigVersion.cmake
foo-config-version.cmake
```

### Search module mode
```
FindFoo.cmake # in ${CMKAE_MODULE_PATH}
```

### Imported Targets

## include(FetchContent)
```
FetchContent_Declare()
FetchContent_MakeAvailable()
```

## include(FindPkgConfig)
```
pkg_check_modules()
pkg_search_module()
pkg_get_variable()
```
