cmake_minimum_required(VERSION 3.10)

project(ftplib VERSION 0.901)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_FIND_LIBRARY_SUFFIXES ".a")
set(BUILD_SHARED_LIBS OFF)
set(CMAKE_EXE_LINKER_FLAGS "-static")

#
add_definitions(-DNOSSL)
add_library(ftplibpp  ftplib.cpp)
add_executable(sample sample/sample.cpp )
message("This is message")

target_include_directories(sample
	PUBLIC "${PROJECT_BINARY_DIR}"
	PUBLIC "${PROJECT_SOURCE_DIR}"
	PUBLIC sample)

target_link_libraries(ftplibpp
	PUBLIC ws2_32)

target_link_libraries(sample
	PUBLIC ftplibpp
	PUBLIC ws2_32)
