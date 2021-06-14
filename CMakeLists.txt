cmake_minimum_required (VERSION 3.0)

PROJECT(graphic)

#Set the compiler
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_BUILD_TYPE Release)
set( EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#set( LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

IF(EXISTS ${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup()
ENDIF()
# set(WITH_VTK ON)
# Requires OpenCV
FIND_PACKAGE( OpenCV 4.0.0 REQUIRED )
MESSAGE("OpenCV version : ${OpenCV_VERSION}")

include_directories(${OpenCV_INCLUDE_DIRS})
link_directories(${OpenCV_LIB_DIR})

ADD_EXECUTABLE( ${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/src/main.cpp )
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS} )

ADD_EXECUTABLE( ch3_sample1 ${PROJECT_SOURCE_DIR}/src/sample1.cpp )
TARGET_LINK_LIBRARIES( ch3_sample1 ${OpenCV_LIBS} )

ADD_EXECUTABLE( ch3_sample2 ${PROJECT_SOURCE_DIR}/src/sample2.cpp )
TARGET_LINK_LIBRARIES( ch3_sample2 ${OpenCV_LIBS} )

ADD_EXECUTABLE( ch3_sample3 ${PROJECT_SOURCE_DIR}/src/sample3.cpp )
TARGET_LINK_LIBRARIES( ch3_sample3 ${OpenCV_LIBS} )

ADD_EXECUTABLE( ch3_sample4 ${PROJECT_SOURCE_DIR}/src/sample4.cpp )
TARGET_LINK_LIBRARIES( ch3_sample4 ${OpenCV_LIBS} )

ADD_EXECUTABLE( ch3_sample5 ${PROJECT_SOURCE_DIR}/src/sample5.cpp )
TARGET_LINK_LIBRARIES( ch3_sample5 ${OpenCV_LIBS} -lglut -lGL -lGLU)

ADD_EXECUTABLE( ch3_sample6 ${PROJECT_SOURCE_DIR}/src/sample6.cpp )
TARGET_LINK_LIBRARIES( ch3_sample6 ${OpenCV_LIBS} )