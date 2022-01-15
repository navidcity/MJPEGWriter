add_library(${PROJECT_NAME} SHARED MJPEGWriter.cpp)

find_package(Threads REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE Threads::Threads)

include_directories(/home/navidcity/ProgramFiles/OpenCV/4.2.0/include/opencv4)
target_link_libraries(${PROJECT_NAME} PRIVATE
    /home/navidcity/ProgramFiles/OpenCV/4.2.0/lib/libopencv_core.so
    /home/navidcity/ProgramFiles/OpenCV/4.2.0/lib/libopencv_highgui.so)
