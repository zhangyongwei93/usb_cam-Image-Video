cmake_minimum_required(VERSION 2.8)
project(video_record)  

## Find catkin and any catkin packages
find_package(catkin REQUIRED COMPONENTS
   roscpp
   rospy
   std_msgs
   genmsg
   sensor_msgs
   cv_bridge
   image_transport  
)

find_package(OpenCV REQUIRED)  

catkin_package()

include_directories(${catkin_INCLUDE_DIRS})

add_executable(video_record_node src/video.cpp)  
target_link_libraries(video_record_node ${catkin_LIBRARIES} ${OpenCV_LIBS}) 
