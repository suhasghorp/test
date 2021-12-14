cmake_minimum_required(VERSION 3.0.0)
project(cmake-test VERSION 0.1.0)
set(CMAKE_CXX_STANDARD 20)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror -Wall")

set(SOURCE_FILES src/main/main.cpp)

set(LIBRARY_NAME cpplib)

include_directories(src/lib)

# Subdirectories to build
add_subdirectory(src/lib)
add_subdirectory(src/tests)

# Name of executable
add_executable(${PROJECT_NAME} ${SOURCE_FILES})

# Link
target_link_libraries(${PROJECT_NAME} ${LIBRARY_NAME})


