cmake_minimum_required(VERSION 3.27)
project(nfd LANGUAGES C CXX)

if(UNIX AND NOT APPLE)

build_library(
    DIRECTORIES src
    PACKAGES gtk
    LINK_PACKAGES gtk::gtk
)

endif(UNIX AND NOT APPLE)


if(WIN32)

build_library(
    DIRECTORIES src
)

endif(WIN32)

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_LIST_DIR} ${CMAKE_CURRENT_LIST_DIR}/engine3d-ndf)

install(TARGETS ${PROJECT_NAME})