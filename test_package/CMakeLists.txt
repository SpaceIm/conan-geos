cmake_minimum_required(VERSION 3.1)
project(test_package C)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(geos CONFIG REQUIRED geos_c)

add_executable(${PROJECT_NAME} test_package.c)
target_link_libraries(${PROJECT_NAME} GEOS::geos_c)
