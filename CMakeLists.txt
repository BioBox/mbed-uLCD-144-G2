
set(CMAKE_TRY_COMPILE_TARGET_TYPE "STATIC_LIBRARY")
set(MBED_PATH ${PROJECT_SOURCE_DIR}/../os/mbed-os/ CACHE INTERNAL "")
set(MBED_CONFIG_PATH ${CMAKE_CURRENT_BINARY_DIR}/.. CACHE INTERNAL "")

include(${MBED_PATH}/tools/cmake/app.cmake)

add_library(ulcd 
    uLCD_4DGL_Graphics.cpp
    uLCD_4DGL_Media.cpp
    uLCD_4DGL_Text.cpp
    uLCD_4DGL_main.cpp
)

target_include_directories(ulcd INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(ulcd mbed-os)
set_target_properties(ulcd PROPERTIES LINKER_LANGUAGE CXX)
