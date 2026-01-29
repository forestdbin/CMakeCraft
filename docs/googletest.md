# Google Test

```
mkdir -p ext/sources
cd ext/sources
git clone https://github.com/google/googletest.git
cd googletest
git checkout -b v1.14.0 v1.14.0

cmake -S . -B out -DCMAKE_INSTALL_PREFIX=~/git/CMakeCraft/ext/googletest
cmake --build out -t install
```
