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
