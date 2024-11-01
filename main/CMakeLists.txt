cmake_minimum_required(VERSION 3.5.1)

message(STATUS "Building SUN")


set(CMAKE_CXX_STANDARD 14)

# 如果编译器不支持 C++11，则让配置过程失败
set(CMAKE_CXX_STANDARD_REQUIRED NO)


find_package(wxWidgets REQUIRED)
find_package(jsoncpp CONFIG REQUIRED)


set(wxWidgets_USE_DEBUG ON)
set(wxWidgets_USE_UNICODE ON)
#find_package(wxWidgets REQUIRED net gl core base)
find_package(wxWidgets REQUIRED)


include(${wxWidgets_USE_FILE})
include_directories(include)


include_directories(${JSON_INC_PATH})#通过这个来添加库
message(STATUS ${JSON_INC_PATH})
add_executable(main src/main.cpp src/MainPanel.cpp)

target_sources(main PRIVATE src/main.cpp)
target_link_libraries(main PRIVATE ${wxWidgets_LIBRARIES} jsoncpp_lib)



