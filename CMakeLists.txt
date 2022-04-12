cmake_minimum_required(VERSION 3.14)

project(sds C)

add_library(${PROJECT_NAME} STATIC
    "sds.c"
    "sds.h"
    "sdsalloc.h")

target_include_directories(
    ${PROJECT_NAME} PUBLIC "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>")

configure_file(FooBarConfig.cmake.in
  "${PROJECT_BINARY_DIR}/FooBarConfig.cmake" @ONLY)
