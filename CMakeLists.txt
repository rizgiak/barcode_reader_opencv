cmake_minimum_required (VERSION 2.6)
project (barcode_reader_opencv)

set(CMAKE_MODULE_PATH ${ZBARCV_SOURCE_DIR})
find_package (OpenCV)
find_package (ZBar0)


add_executable (barcode_reader main.cpp)
target_link_libraries (barcode_reader ${OpenCV_LIBRARIES} ${ZBAR_LIBRARIES})
