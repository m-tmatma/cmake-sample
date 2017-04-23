cmake_minimum_required(VERSION 2.6.4)

project (LibraryTest)

set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT "Program" )

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})

add_subdirectory(Library)
add_subdirectory(Program)

# turn on solution folder
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# create solution folder
set_target_properties(Library     PROPERTIES FOLDER library)
set_target_properties(Program     PROPERTIES FOLDER executable)
