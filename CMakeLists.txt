cmake_minimum_required(VERSION 3.0.0)

project(libwordexp C)

add_library(wordexp_a STATIC wordexp.c reallocarray.c)
add_library(wordexp   SHARED wordexp.c reallocarray.c)

include(GNUInstallDirs)

install(TARGETS wordexp LIBRARY                     DESTINATION ${CMAKE_INSTALL_LIBDIR})
install(FILES ${PROJECT_BINARY_DIR}/libwordexp_a.a  DESTINATION ${CMAKE_INSTALL_LIBDIR})
install(FILES ${PROJECT_SOURCE_DIR}/libwordexp.h    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
