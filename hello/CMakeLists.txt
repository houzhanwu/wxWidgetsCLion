cmake_minimum_required(VERSION 3.5.1)

message(STATUS "Building SUN")


find_package(wxWidgets REQUIRED)



set(wxWidgets_USE_DEBUG ON)
set(wxWidgets_USE_UNICODE ON)
find_package(wxWidgets REQUIRED net gl core base)

include(${wxWidgets_USE_FILE})

add_executable(app src/app.cpp)

target_sources(app PRIVATE
        src/app.cpp)

target_link_libraries(app PRIVATE ${wxWidgets_LIBRARIES})


