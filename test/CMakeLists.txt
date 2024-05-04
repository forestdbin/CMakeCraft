set(GTest_DIR ~/git/CMakeCraft/ext/googletest/lib/cmake/GTest)
find_package(GTest)

add_executable(
    main_test
    main_test.cpp
)

target_link_libraries(
    main_test
    GTest::gtest_main
)

## this is a general way to add test
# include(CTest)
# add_test(foo main_test)

## this is specific to googletest
# enable_testing()
include(GoogleTest)
gtest_discover_tests(main_test)
