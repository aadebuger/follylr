#make_minimum_required(VERSION 3.7)
cmake_minimum_required(VERSION 3.24)
project(HelloWorld)
#find_package(Boost REQUIRED)
#find_package(folly REQUIRED)
#find_package(Threads REQUIRED)
find_package(Boost REQUIRED COMPONENTS context )
find_package(glog REQUIRED)
find_package(gflags REQUIRED)
#set(CMAKE_CXX_STANDARD 14)
#include_directories(${Boost_INCLUDE_DIRS})

#set_and_check(FOLLY_INCLUDE_DIR  /opt/homebrew/Cellar/folly/2022.09.05.00/include)
#set_and_check(FOLLY_CMAKE_DIR /opt/homebrew/Cellar/folly/2022.09.05.00/lib/cmake/folly)
#if (NOT TARGET Folly::folly)
#  include("${FOLLY_CMAKE_DIR}/folly-targets.cmake")
#endif()

include_directories(/opt/homebrew/Cellar/folly/2022.09.05.00/include)

include_directories(/opt/homebrew/include)
set(FOLLY_LIBRARIES Folly::folly)

#if (NOT folly_FIND_QUIETLY)
#  message(STATUS "Found folly: ${PACKAGE_PREFIX_DIR}")
#endif()
#set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14" )
add_executable(HelloWorld main.cpp)
message(STATUS  "${GFLAGS_LIBRARIES}") 
message(STATUS "${GLOG_LIBRARIES}")
target_link_libraries(HelloWorld  Boost::context  ${GFLAGS_LIBRARIES} c++abi pthread /opt/homebrew/Cellar/libevent/2.1.12/lib/libevent.a  /opt/homebrew/Cellar/double-conversion/3.2.1/lib/libdouble-conversion.a  /opt/homebrew/Cellar/fmt/9.1.0/lib/libfmt.a  /opt/homebrew/Cellar/gflags/2.2.2/lib/libgflags.dylib /opt/homebrew/Cellar/glog/0.6.0/lib/libglog.dylib  /opt/homebrew/Cellar/folly/2022.09.05.00/lib/libfolly.a)
