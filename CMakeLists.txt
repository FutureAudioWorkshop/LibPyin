cmake_minimum_required(VERSION 3.10)
project(LibPyin)
set (CMAKE_CXX_STANDARD 11)

include_directories(./source/)

aux_source_directory(./source/vamp SRC_LIST)
aux_source_directory(./source/vamp-sdk SRC_LIST)
aux_source_directory(./source/pyin SRC_LIST)

# Don't force build type — inherit from parent project to avoid runtime library mismatches

# Change SHARED to STATIC here
add_library(LibPyin STATIC ${SRC_LIST} ./source/normal_dist_pdf.cpp ./source/libpyincpp.cpp ./source/libpyinc.cpp)
