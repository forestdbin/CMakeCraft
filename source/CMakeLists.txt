find_package(
    nlohmann_json
    REQUIRED ALL
    PATHS ~/git/CMakeCraft/ext/json/share/cmake
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
)
