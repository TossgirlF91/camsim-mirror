# Copyright (C) 2017, 2018
# Computer Graphics Group, University of Siegen
# Written by Martin Lambers <martin.lambers@uni-siegen.de>
#
# Copying and distribution of this file, with or without modification, are
# permitted in any medium without royalty provided the copyright notice and this
# notice are preserved. This file is offered as-is, without any warranty.

cmake_minimum_required(VERSION 3.4)
set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR} ${CMAKE_MODULE_PATH})
set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

project(camsim-pmd-example)

if(CMAKE_COMPILER_IS_GNUCXX)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -Wall -Wextra")
endif()

find_package(Qt5 5.6.0 COMPONENTS Gui)
find_package(CamSim REQUIRED)

include_directories(${CAMSIM_INCLUDE_DIRS})
link_directories(${CAMSIM_LIBRARY_DIRS})
add_executable(camsim-pmd-example camsim-pmd-example.cpp)
target_link_libraries(camsim-pmd-example ${CAMSIM_LIBRARIES} Qt5::Gui)
install(TARGETS camsim-pmd-example RUNTIME DESTINATION bin)
