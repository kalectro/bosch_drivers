cmake_minimum_required(VERSION 2.8.3)
project(bmc050_driver)

find_package(catkin REQUIRED COMPONENTS roscpp bosch_drivers_common)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES bmc050
)

## Specify additional locations of header files
include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_library(bmc050 src/bmc050.cpp)
add_library(bmc050_parameters src/bmc050_parameters.cpp)
target_link_libraries(bmc050 bmc050_parameters)

install(TARGETS bmc050 bmc050_parameters DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})