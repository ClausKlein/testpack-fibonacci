cmake_minimum_required(VERSION 3.21...3.26 FATAL_ERROR)

project(TestFibonacci LANGUAGES CXX)

# ---- Options ----

# ---- Dependencies ----

include(../cmake/CPM.cmake)

CPMAddPackage(NAME Fibonacci SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/.. SYSTEM NO)
# XXX add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/.. Fibonacci)

# ---- Create binary ----

add_executable(TestFibonacci main.cpp)
target_link_libraries(TestFibonacci fibonacci)
set_target_properties(TestFibonacci PROPERTIES CXX_STANDARD 17 COMPILE_FLAGS "-Wall -Wpedantic -Wextra -Werror -Wextra-semi")

