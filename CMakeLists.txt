cmake_minimum_required(VERSION 2.8.3)
project(lemon_app)

find_package(catkin REQUIRED COMPONENTS roscpp)

find_package(LEMON REQUIRED)

catkin_package(
    CATKIN_DEPENDS roscpp
    DEPENDS LEMON
)

include_directories(
    ${catkin_INCLUDE_DIRS}
    ${LEMON_INCLUDE_DIRS}
)

add_executable(hello_lemon src/hello_lemon.cpp)

target_link_libraries(hello_lemon
    ${catkin_LIBRARIES}
    ${LEMON_LIBRARIES}
)
