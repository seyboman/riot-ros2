cmake_minimum_required(VERSION 3.5)

project(riot)

include(ExternalProject)

find_package(ament_cmake REQUIRED)

ExternalProject_Add(RIOT
    GIT_REPOSITORY https://github.com/seyboman/RIOT.git
    #GIT_TAG feature/ndn-riot-run-once
    GIT_TAG feature/mechaduino-board

    SOURCE_DIR RIOT

    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND ""
    LOG_DOWNLOAD ON
    )

install(
    DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/RIOT
    DESTINATION .
    USE_SOURCE_PERMISSIONS
    )

ament_package()
