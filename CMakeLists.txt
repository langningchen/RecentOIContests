cmake_minimum_required(VERSION 3.9)
project(RecentOIContests)

set(CMAKE_CXX_COMPILER "g++")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=c++14")

add_executable(RecentOIContests
    Lib/Exception.cpp
    Lib/Curl.cpp
    Lib/StringOperation.cpp
    main.cpp)
target_include_directories(RecentOIContests PUBLIC Lib)

find_library(LIBCURL curl REQUIRED)
set(LIBS
    ${LIBCURL}
)
target_link_libraries(RecentOIContests PRIVATE ${LIBS})
