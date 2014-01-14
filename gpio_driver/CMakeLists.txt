cmake_minimum_required(VERSION 2.8.3)
project(gpio_driver)

find_package(catkin REQUIRED COMPONENTS roscpp bosch_drivers_common)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES gpio_driver
)

## Specify additional locations of header files
include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_library(gpio_driver src/gpio_driver.cpp)

target_link_libraries(gpio_driver ${catkin_LIBRARIES})

install(TARGETS ${PROJECT_NAME}
        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
        ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})
