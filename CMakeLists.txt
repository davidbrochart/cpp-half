cmake_minimum_required(VERSION 3.7.2)
project(halfFloat)

include(GNUInstallDirs)

add_library(half_float INTERFACE)
target_include_directories(half_float INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>)

include(CMakePackageConfigHelpers)
include(GNUInstallDirs)

install(DIRECTORY include/ DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
install(TARGETS half_float EXPORT halfFloatConfig)
install(EXPORT halfFloatConfig NAMESPACE halfFloat:: DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/halfFloat)
