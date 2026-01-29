# nlohmann json

```bash
cd ext/source
git clone https://github.com/nlohmann/json.git
cd json
git checkout v3.12.0

cmake -S . -B out -DJSON_BuildTests=OFF -DJSON_MultipleHeaders=OFF
cmake --build out
cmake --install out --prefix ../../json
```
