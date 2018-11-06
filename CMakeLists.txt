cmake_minimum_required(VERSION 2.8)

# The project name
project( DIP_HW03 )

# Find OpenCV Package and include it
find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )

# Set C++ 11
set( CMAKE_CXX_STANDARD 11 )
set( CMAKE_CXX_STANDARD_REQUIRED ON )
set( CMAKE_CXX_EXTENSIONS OFF )

# Project sources
set ( SOURCE_DIR src )
set ( PROJECT_SOURCES 
    ${SOURCE_DIR}/common.h 
    ${SOURCE_DIR}/common.cpp 
    ${SOURCE_DIR}/BaseProcessor.h
    ${SOURCE_DIR}/BaseProcessor.cpp
    ${SOURCE_DIR}/GeometricTransformProcessor.h
    ${SOURCE_DIR}/GeometricTransformProcessor.cpp
)

# The main program
add_executable( DIP_HW03 ${SOURCE_DIR}/main.cpp ${PROJECT_SOURCES} )

# Add link libraries
target_link_libraries( DIP_HW03 ${OpenCV_LIBS} )
