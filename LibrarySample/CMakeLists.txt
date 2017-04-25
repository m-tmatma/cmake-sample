cmake_minimum_required(VERSION 2.6.4)

# see https://cmake.org/Wiki/BuildingWinDLL
# Allow the developer to select if Dynamic or Static libraries are built
option (BUILD_SHARED_LIBS "Build Shared Libraries" ON)
# Set the LIB_TYPE variable to STATIC
set (LIB_TYPE STATIC)
if (BUILD_SHARED_LIBS)
  # User wants to build Dynamic Libraries, so change the LIB_TYPE variable to CMake keyword 'SHARED'
  set (LIB_TYPE SHARED)
endif (BUILD_SHARED_LIBS)

project (LibraryTest)

set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT "sample_program" )

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

add_subdirectory(Library)
add_subdirectory(Program)

# turn on solution folder
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# create solution folder
set_target_properties(Library        PROPERTIES FOLDER library)
set_target_properties(sample_program PROPERTIES FOLDER executable)
