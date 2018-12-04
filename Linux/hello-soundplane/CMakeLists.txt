cmake_minimum_required(VERSION 3.2)

project(hello-soundplane)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

if(NOT "${CMAKE_BUILD_TYPE}" STREQUAL "Release")
  add_definitions(-DDEBUG)
endif()

#add_subdirectory(${SP_MADRONALIB_DIR} madronalib)
add_subdirectory(SoundplaneLib)

set(HSP_SOURCES
    main.cpp
)