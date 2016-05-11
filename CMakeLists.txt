cmake_minimum_required(VERSION 2.8)
project(fbcp)

find_package(PkgConfig)
PKG_CHECK_MODULES(EGL egl)

include_directories(${EGL_INCLUDE_DIRS})
add_executable(${PROJECT_NAME} main.c)
target_link_libraries(${PROJECT_NAME} ${EGL_LIBRARIES})

install(TARGETS ${PROJECT_NAME} DESTINATION bin)
