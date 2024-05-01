add_subdirectory(greet)

add_executable(
    foo
    main.cpp
)

target_link_libraries(
    foo
    greet
)
