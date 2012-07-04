cmake_minimum_required(VERSION 2.6)

# Locate GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

# Add what we want to test
add_subdirectory(whattotest)

# Link runTests with what we want to test and the GTest and pthread library
add_executable(runUnitTests tests.cpp)
target_link_libraries(runUnitTests whattotest ${GTEST_LIBRARIES} pthread)
