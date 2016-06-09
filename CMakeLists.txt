ExternalProject_Add(websocketpp
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=<INSTALL_DIR>
    SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/websocketpp
)

ExternalProject_Add(cxx-util
    DEPENDS websocketpp
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=<INSTALL_DIR>
    SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/cxx-util
)

ExternalProject_Add(nanopb
    #URL "http://koti.kapsi.fi/~jpa/nanopb/download/nanopb-0.3.5-windows-x86.zip"
    URL "https://s3.amazonaws.com/barobo/deps/nanopb-0.3.5-windows-x86.zip"
    URL_MD5 "edf923dd23f87c75caecb5401e1b07c5"
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND ""
)

ExternalProject_Get_Property(nanopb SOURCE_DIR)
set(NANOPB_ROOT ${SOURCE_DIR})

ExternalProject_Add(ribbon-bridge
    DEPENDS nanopb
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=<INSTALL_DIR> -DNANOPB_ROOT=${NANOPB_ROOT}
    SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/ribbon-bridge
)

ExternalProject_Add(interfaces
    DEPENDS ribbon-bridge
    CMAKE_ARGS -DCMAKE_INSTALL_PREFIX=<INSTALL_DIR> -DNANOPB_ROOT=${NANOPB_ROOT}
    SOURCE_DIR ${CMAKE_CURRENT_LIST_DIR}/interfaces
)
