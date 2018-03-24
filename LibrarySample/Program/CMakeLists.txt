cmake_minimum_required(VERSION 2.6.4)

# define a variable of project name
set( project_name sample_program)

# set the project as the startup project
set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT ${project_name} )

# define a project name
project (${project_name})

# define a variable SRC with file GLOB
file(GLOB SRC *.c *.h)

set(external_projs ${external_projs} Library)

# https://cmake.org/cmake/help/v3.0/command/foreach.html
foreach(loop_var IN LISTS external_projs)
	# add include directory
	# https://cmake.org/cmake/help/v3.0/variable/PROJECT-NAME_SOURCE_DIR.html
	include_directories(${${loop_var}_SOURCE_DIR})

	# add include directory for ${project_name}_Export.h
	# https://cmake.org/cmake/help/v3.0/variable/PROJECT-NAME_BINARY_DIR.html
	include_directories(${${loop_var}_BINARY_DIR})
endforeach()

## add include directory
## https://cmake.org/cmake/help/v3.0/variable/PROJECT-NAME_SOURCE_DIR.html
#include_directories(${Library_SOURCE_DIR})
#
## add include directory for ${project_name}_Export.h
## https://cmake.org/cmake/help/v3.0/variable/PROJECT-NAME_BINARY_DIR.html
#include_directories(${Library_BINARY_DIR})

# define sources files of an executable
add_executable(${project_name} ${SRC})

# link a library
foreach(loop_var IN LISTS external_projs)
	target_link_libraries(${project_name} ${loop_var})
endforeach()
#target_link_libraries(${project_name} Library)
