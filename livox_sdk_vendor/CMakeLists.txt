cmake_minimum_required(VERSION 3.9)

project(livox_sdk_vendor)

find_package(ament_cmake REQUIRED)

set(CMAKE_POSITION_INDEPENDENT_CODE On)
add_subdirectory(external/livox_sdk)

install(TARGETS livox_sdk_static
        EXPORT export_${PROJECT_NAME}
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib)

ament_export_targets(export_${PROJECT_NAME} HAS_LIBRARY_TARGET)
ament_package()
