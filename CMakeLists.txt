cmake_minimum_required(VERSION 3.10)
project(uint256_t)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/uint128_t)

add_library(uint256_t STATIC ${CMAKE_CURRENT_SOURCE_DIR}/uint256_t.cpp)
target_include_directories(uint256_t PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/uint128_t
)
target_link_libraries(uint256_t PRIVATE uint128_t)