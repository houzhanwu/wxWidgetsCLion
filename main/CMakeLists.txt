cmake_minimum_required(VERSION 3.5.1)

message(STATUS "Building SUN")


set(CMAKE_CXX_STANDARD 14)

# 如果编译器不支持 C++11，则让配置过程失败
set(CMAKE_CXX_STANDARD_REQUIRED NO)


find_package(wxWidgets REQUIRED)



set(wxWidgets_USE_DEBUG ON)
set(wxWidgets_USE_UNICODE ON)
find_package(wxWidgets REQUIRED net gl core base)

include(${wxWidgets_USE_FILE})
#include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(include)



add_executable(main src/main.cpp)

#target_include_directories(main PRIVATE include)


target_sources(main PRIVATE src/main.cpp)
target_link_libraries(main PRIVATE ${wxWidgets_LIBRARIES})


