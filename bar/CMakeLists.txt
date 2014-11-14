cmake_minimum_required(VERSION 2.8)
project(bar CXX)

find_package(Foo REQUIRED)

include_directories(${FOO_INCLUDE_DIRS})

add_executable(bar bar.cpp)

target_link_libraries(bar ${FOO_LIBRARIES})

install(TARGETS bar RUNTIME DESTINATION bin)
