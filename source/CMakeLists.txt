# set(nlohmann_json_DIR ${CMAKE_SOURCE_DIR}/ext/json/share/cmake/nlohmann_json)
# set(nlohmann_json_ROOT ${CMAKE_SOURCE_DIR}/ext/json)
find_package(
    nlohmann_json
    REQUIRED
    PATHS ${CMAKE_SOURCE_DIR}/ext/json
)

# set(Boost_DIR ${CMAKE_SOURCE_DIR}/ext/boost/lib/cmake/Boost-1.90.0)
# set(Boost_ROOT ${CMAKE_SOURCE_DIR}/ext/boost)
find_package(
    Boost
    REQUIRED ALL
    PATHS ${CMAKE_SOURCE_DIR}/ext/boost
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
