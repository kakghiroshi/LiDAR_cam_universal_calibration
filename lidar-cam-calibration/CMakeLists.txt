cmake_minimum_required(VERSION 3.16)
project(lidar-cam-calibration)
find_package(OpenCV REQUIRED)
find_package(PCL REQUIRED)
find_package(Ceres REQUIRED)
set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")
include_directories( ${OpenCV_INCLUDE_DIRS})
include_directories(${PCL_INCLUDE_DIRS} include)

link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

add_executable(lidar_camera_p_plane ./src/lidar_camera_p_plane.cpp)
target_link_libraries(lidar_camera_p_plane ${PCL_LIBRARIES} ${OpenCV_LIBS} ${CERES_LIBRARIES})

add_executable(lidar_camera_p_plane_fisheye ./src/lidar_camera_p_plane_fisheye.cpp)
target_link_libraries(lidar_camera_p_plane_fisheye ${PCL_LIBRARIES} ${OpenCV_LIBS} ${CERES_LIBRARIES})



