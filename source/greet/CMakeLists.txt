add_library(
    greet SHARED
    greet.cpp
)

target_include_directories(
    greet
    PUBLIC .
)
