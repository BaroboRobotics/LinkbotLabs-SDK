cmake_minimum_required(VERSION 3.2.1)
project(LinkbotLabs-SDK VERSION 0.1.0)

add_subdirectory(cxx-util EXCLUDE_FROM_ALL)
add_subdirectory(libsfp EXCLUDE_FROM_ALL)
add_subdirectory(ribbon-bridge EXCLUDE_FROM_ALL)
add_subdirectory(baromesh EXCLUDE_FROM_ALL)

add_subdirectory(libstkcomms EXCLUDE_FROM_ALL)