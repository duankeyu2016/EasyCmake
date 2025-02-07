cmake_minimum_required(VERSION 3.20)

project(EasyCmake)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(cmake/easy.cmake)

e_init_cmake()

set(LIB_OUT_DIR ${CMAKE_BINARY_DIR}/bin)


set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${LIB_OUT_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${LIB_OUT_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELWITHDEBINFO ${LIB_OUT_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_MINSIZEREL ${LIB_OUT_DIR})

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${LIB_OUT_DIR})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${LIB_OUT_DIR})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELWITHDEBINFO ${LIB_OUT_DIR})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_MINSIZEREL ${LIB_OUT_DIR})

if (NOT WIN32)
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_DEBUG ${LIB_OUT_DIR})
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_RELEASE ${LIB_OUT_DIR})
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_RELWITHDEBINFO ${LIB_OUT_DIR})
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_MINSIZEREL ${LIB_OUT_DIR})
endif ()

add_subdirectory(tests/library)
