cmake_minimum_required(VERSION 3.13)

set(PICO_BOARD_HEADER_DIRS "${CMAKE_CURRENT_LIST_DIR}/src/boards")
set(PICO_BOARD leverless-fightstick)

include(pico_sdk_import.cmake)

project(leverless)

pico_sdk_init()

add_executable(leverless-fightstick src/leverless.c)
target_include_directories(leverless-fightstick PRIVATE src)
target_link_libraries(leverless-fightstick pico_stdlib tinyusb_device tinyusb_board)
target_compile_definitions(leverless-fightstick-rev5 PRIVATE FIGHTSTICK)
pico_add_extra_outputs(leverless-fightstick)
