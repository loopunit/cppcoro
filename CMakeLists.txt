cmake_minimum_required(VERSION 3.11)
project(cppcoro LANGUAGES CXX)

file(GLOB sources
	${CMAKE_CURRENT_LIST_DIR}/lib/*.cpp
	${CMAKE_CURRENT_LIST_DIR}/include/*.hpp
	${CMAKE_CURRENT_LIST_DIR}/detail/*.hpp
	${CMAKE_CURRENT_LIST_DIR}/net/*.hpp)
add_library(cppcoro ${sources})

target_include_directories(cppcoro PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")
set_property(TARGET cppcoro PROPERTY CXX_STANDARD 20)
set_property(TARGET cppcoro PROPERTY CXX_STANDARD_REQUIRED ON)
set_property(TARGET cppcoro PROPERTY CXX_EXTENSIONS OFF)
target_compile_options(cppcoro PUBLIC "/await")
