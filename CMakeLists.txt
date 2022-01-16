
cmake_minimum_required(VERSION 3.9)

# Define the project name, language, version and description
project(MJPEGWriter
    LANGUAGES CXX
    VERSION 0.0.1
    DESCRIPTION "OpenCV Video HTTP Streaming via MJPEG")

# Set required C++ standard
set(CMAKE_CXX_STANDARD 14)

include(GNUInstallDirs)

add_subdirectory(src)
target_include_directories(${PROJECT_NAME} PRIVATE .)

set_target_properties(${PROJECT_NAME} PROPERTIES VERSION ${PROJECT_VERSION})
set_target_properties(${PROJECT_NAME} PROPERTIES SOVERSION ${PROJECT_VERSION_MAJOR})

set_target_properties(${PROJECT_NAME} PROPERTIES PUBLIC_HEADER include/MJPEGWriter.h)

install(TARGETS ${PROJECT_NAME}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})

configure_file(MJPEGWriter.pc.in MJPEGWriter.pc @ONLY)
install(FILES ${CMAKE_BINARY_DIR}/MJPEGWriter.pc DESTINATION ${CMAKE_INSTALL_DATAROOTDIR}/pkgconfig)
