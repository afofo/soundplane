cmake_minimum_required(VERSION 3.2)
project(hello-soundplane)

set(EXECUTABLE_NAME "hello-soundplane")

set(SP_USE_LIBUSB true)

set(SP_SOUNDPLANELIB_DIR "${CMAKE_SOURCE_DIR}/../../SoundplaneLib")
message("SP_SOUNDPLANELIB_DIR: ${SP_SOUNDPLANELIB_DIR}")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

if(NOT "${CMAKE_BUILD_TYPE}" STREQUAL "Release")
  add_definitions(-DDEBUG)
endif()

add_subdirectory(${SP_SOUNDPLANELIB_DIR} SoundplaneLib)

set(HSP_SOURCES
    main.cpp
)

add_executable(${EXECUTABLE_NAME}
  ${HSP_SOURCES}
)

target_link_libraries(${EXECUTABLE_NAME}
  soundplanelib
)