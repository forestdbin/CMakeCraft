find_package(
    nlohmann_json
    REQUIRED ALL
    PATHS ~/git/CMakeCraft/ext/json/share/cmake
)

find_package(
    Boost
    REQUIRED ALL
    PATHS ~/git/CMakeCraft/ext/boost/lib/cmake
)

add_subdirectory(greet)

add_executable(
    foo
    main.cpp
)

target_link_libraries(
    foo
    PRIVATE greet
    PRIVATE nlohmann_json::nlohmann_json
    PRIVATE Boost::unit_test_framework
)
