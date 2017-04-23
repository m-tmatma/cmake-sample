cmake_minimum_required(VERSION 2.6.4)

# define a variable of project name
set( project_name "Program")

# set the project as the startup project
set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT ${project_name} )

# define a project name
project (${project_name})

# define a variable SRC with file GLOB
file(GLOB SRC *.c *.h)

# add include directory
include_directories(../Library)

# add include directory for ${project_name}_Export.h
include_directories(${PROJECT_BINARY_DIR}/../Library)

# define sources files of an executable
add_executable(${project_name} ${SRC})

# link a library
target_link_libraries(${project_name} Library)
