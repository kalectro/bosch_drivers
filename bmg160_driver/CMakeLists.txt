cmake_minimum_required(VERSION 2.8.3)
project(bmg160_driver)

find_package(catkin REQUIRED COMPONENTS roscpp bosch_drivers_common)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES bmg160
)

## Specify additional locations of header files
include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_library(bmg160 src/bmg160.cpp)
add_library(bmg160_parameters src/bmg160_parameters.cpp)
target_link_libraries(bmg160 bmg160_parameters)

install(TARGETS bmg160 bmg160_parameters DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})