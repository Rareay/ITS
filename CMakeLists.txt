cmake_minimum_required(VERSION 2.8)
project(trslam)

set(CMAKE_BUILD_TYPE Release)

set(CMAKE_CXX_FLAGS "-std=c++11 -Wall")
set(CMAKE_CXX_FLAGS_RELEASE  "-std=c++11 -O3 -fopenmp -pthread")

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

############### dependencies ######################

# OpenCV
find_package(OpenCV 3.4.7 REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# Boost
#find_package(Boost REQUIRED)
find_package(Boost REQUIRED COMPONENTS filesystem system thread date_time)
include_directories(${Boost_INCLUDE_DIRS})

# pangolin
find_package(Pangolin REQUIRED)
include_directories(${Pangolin_INCLUDE_DIRS})



set(THIRD_PARTY_LIBS
        ${OpenCV_LIBS}
        ${Boost_LIBRARIES}
        ${Pangolin_LIBRARIES} GL GLU GLEW glut
        dl glfw3 X11 Xrandr Xi
        pthread
        )

enable_testing()


############### source and test ######################
include_directories(${PROJECT_SOURCE_DIR}/include)

add_subdirectory(src)   # 编译库
add_subdirectory(test)  # 编译测试
#add_subdirectory(app)   # 编译app
