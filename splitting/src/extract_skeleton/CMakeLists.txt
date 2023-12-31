# Created by the script cgal_create_cmake_script
# This is the CMake script for compiling a CGAL application.

cmake_minimum_required(VERSION 3.1...3.23)
project(Extract_Skeleton)

find_package(CGAL REQUIRED OPTIONAL_COMPONENTS Qt5)

# create a target per cppfile
file(
  GLOB cppfiles
  RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)
foreach(cppfile ${cppfiles})
  create_single_source_cgal_program("${cppfile}")
endforeach()

set_target_properties(${PROJECT_NAME}
    PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
)

if(CGAL_Qt5_FOUND)
  target_link_libraries(draw_triangulation_2 PUBLIC CGAL::CGAL_Basic_viewer)
    target_link_libraries(star_conflict_zone PUBLIC CGAL::CGAL_Basic_viewer)
else()
  message(
    STATUS
      "NOTICE: The example draw_triangulation_2 requires Qt and will not be compiled."
  )
endif()
