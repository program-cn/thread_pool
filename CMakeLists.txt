cmake_minimum_required(VERSION 3.10)
project(test_system)

set(CMAKE_CXX_STANDARD 11)

find_package(Boost REQUIRED COMPONENTS iostreams)

set(ALL_LIB lib_thread/thread_pool.cc lib_thread/task.cc lib_thread/time.cc)

add_executable(test_system main.cpp ${ALL_LIB})
target_link_libraries(test_system PUBLIC ${Boost_LIBRARIES})        #添加boost库
target_link_libraries(test_system PUBLIC  pthread)                  #添加线程库
