# set(GTest_DIR ${CMAKE_SOURCE_DIR}/ext/googletest/lib/cmake/GTest)
# set(GTEST_ROOT ${CMAKE_SOURCE_DIR}/ext/googletest)
# set(GTest_ROOT ${CMAKE_SOURCE_DIR}/ext/googletest)
find_package(GTest REQUIRED
    PATHS ${CMAKE_SOURCE_DIR}/ext/googletest
)

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
