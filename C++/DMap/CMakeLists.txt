cmake_minimum_required(VERSION 3.0)
project(DMap)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")

find_package(RapidJSON)

file(GLOB CXX_EXEC "src/*.cpp")

add_library(DMap SHARED ${CXX_EXEC})
target_include_directories(DMap PUBLIC
                            inc/
                            submodules/rapidjson/include)
