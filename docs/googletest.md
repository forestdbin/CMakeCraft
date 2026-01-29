# Google Test

```bash
cd ext/source
git clone https://github.com/google/googletest.git
cd googletest
git checkout v1.17.0

cmake -S . -B out
cmake --build out
cmake --install out --prefix ../../googletest
```
