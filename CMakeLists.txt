cmake_minimum_required(VERSION 3.2.1)
project(LinkbotLabs-SDK VERSION 0.1.0)

set(AVR OFF)
if(CMAKE_SYSTEM_NAME MATCHES "AVR")
    set(AVR ON)
endif()

add_subdirectory(cxx-util EXCLUDE_FROM_ALL)
add_subdirectory(libsfp EXCLUDE_FROM_ALL)
add_subdirectory(ribbon-bridge EXCLUDE_FROM_ALL)
add_subdirectory(baromesh EXCLUDE_FROM_ALL)

if(NOT AVR)
    add_subdirectory(usbcdc EXCLUDE_FROM_ALL)
    add_subdirectory(libstkcomms EXCLUDE_FROM_ALL)
endif()
