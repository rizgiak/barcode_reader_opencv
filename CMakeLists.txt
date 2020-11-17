cmake_minimum_required (VERSION 2.6)
project (barcode_reader_opencv)

set(CMAKE_MODULE_PATH ${ZBARCV_SOURCE_DIR})
find_package (OpenCV)

find_package(PkgConfig REQUIRED)
pkg_check_modules(ZBar REQUIRED IMPORTED_TARGET zbar)

include_directories(${ZBAR_INCLUDE_DIR})

add_executable (barcode_reader main.cpp)
target_link_libraries (barcode_reader ${OpenCV_LIBRARIES} ${ZBAR_LIBRARIES} PkgConfig::ZBar)

file (COPY ${CMAKE_CURRENT_SOURCE_DIR}/sample-barcode.jpeg DESTINATION ${CMAKE_CURRENT_BINARY_DIR} FILE_PERMISSIONS OWNER_READ)