cmake_minimum_required(VERSION 2.8)
project(foo CXX)

add_library(foo foo.cpp foo.h)

install(TARGETS foo
  LIBRARY DESTINATION lib
  ARCHIVE DESTINATION lib)

install(FILES foo.h DESTINATION include)

configure_file(modules/FooConfig.cmake.in FooConfig.cmake @ONLY)

install(FILES ${CMAKE_CURRENT_BINARY_DIR}/FooConfig.cmake
  DESTINATION lib${LIB_SUFFIX}/cmake/foo)
