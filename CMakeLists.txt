cmake_minimum_required(VERSION 3.14)
project(PR4_2)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(../PR4_2/lib/googletest)

include_directories(/opt/homebrew/opt/ncurses/include)
link_directories(/opt/homebrew/opt/ncurses/lib)

add_executable(PR4_2
        classes/Parallelepiped.cpp
        classes/Parallelepiped.h
        classes/IShape.h
        classes/Sphere.h
        classes/Sphere.cpp
        classes/Tetrahedron.cpp
        classes/Tetrahedron.h
        main.cpp
)

target_link_libraries(PR4_2)

add_executable(PR4_2_tests
        classes/Parallelepiped.cpp
        classes/Parallelepiped.h
        classes/IShape.h
        classes/Sphere.h
        classes/Sphere.cpp
        classes/Tetrahedron.cpp
        classes/Tetrahedron.h
        tests/tests.cpp
)

target_link_libraries(PR4_2_tests gtest gtest_main)

enable_testing()
include(GoogleTest)
gtest_discover_tests(PR4_2_tests)
