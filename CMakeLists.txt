cmake_minimum_required(VERSION 2.8)

SET(COMPILE_DEFINITIONS -Werror)

include_directories(/opt/vc/include)

link_directories(/opt/vc/lib)

add_executable(fbcp main.c)

target_link_libraries(fbcp bcm_host)
