cmake_minimum_required(VERSION 2.8.3)
project(bosch_drivers_common)

find_package(catkin REQUIRED COMPONENTS roscpp)

catkin_package(
  INCLUDE_DIRS include
)

include_directories(include
  ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY
  include
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})