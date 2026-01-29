# Boost

```bash
cd ext/source
wget https://archives.boost.io/release/1.90.0/source/boost_1_90_0.tar.gz
tar xf boost_1_90_0.tar.gz
cd boost_1_90_0

./bootstrap.sh
./b2
./b2 stage
./b2 install --prefix=../../boost
```
