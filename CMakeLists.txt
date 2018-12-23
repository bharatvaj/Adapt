cmake_minimum_required(VERSION 3.0)

project(Adapt)

file(GLOB_RECURSE ADAPT_HDRS "include/*.hpp")
file(GLOB_RECURSE ADAPT_SRCS "src/*.cpp")

find_package(clog)
find_package(crossguid REQUIRED)

add_library(Adapt ${ADAPT_SRCS} ${ADAPT_HDRS})

target_include_directories(Adapt PRIVATE include)
target_include_directories(Adapt PRIVATE crossguid)

target_link_libraries(Adapt crossguid)
