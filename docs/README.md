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
