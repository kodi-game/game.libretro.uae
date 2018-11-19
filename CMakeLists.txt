cmake_minimum_required(VERSION 3.1)
project(game.libretro.uae)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(UAE_LIB NAMES puae_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(UAE_CUSTOM_BINARY ${UAE_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} UAE "")

include(CPack)
