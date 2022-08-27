#-------------------------------------------------------------------#
# cmake version

cmake_minimum_required(VERSION 3.20)

#-------------------------------------------------------------------#
# project config

project(teora_app)

set(CMAKE_AUTOMOC ON)

CopyQtPlatforms()
CopyQtDll("Qt6Core")
CopyQtDll("Qt6Widgets")
CopyQtDll("Qt6Gui")

#-------------------------------------------------------------------#
# project sources

set(SOURCES
    main.cpp
)

#-------------------------------------------------------------------#
# project type

add_executable(${PROJECT_NAME} ${CMAKE_CURRENT_SOURCE_DIR}/${SOURCES})

#-------------------------------------------------------------------#
# target properties

if(WIN32)
    set_target_properties(${PROJECT_NAME} PROPERTIES WIN32_EXECUTABLE TRUE)
endif()

#-------------------------------------------------------------------#
# link libraries

target_link_libraries(${PROJECT_NAME}
    PRIVATE Qt6::Core
    PRIVATE Qt6::Widgets
)

#-------------------------------------------------------------------#