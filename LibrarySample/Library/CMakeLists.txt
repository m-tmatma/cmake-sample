cmake_minimum_required(VERSION 2.6.4)

# define a variable of project name
set( project_name "Library")

# define a project name
project (${project_name})

# define a variable SRC with file GLOB
file(GLOB SRC *.c *.h)

# add include directory for ${project_name}_Export.h
include_directories(${PROJECT_BINARY_DIR})

# define sources files of an executable
add_library(${project_name} SHARED ${SRC} ${PROJECT_BINARY_DIR}/${project_name}_Export.h)

include (GenerateExportHeader)
GENERATE_EXPORT_HEADER( ${project_name}
	BASE_NAME ${project_name}
	EXPORT_MACRO_NAME ${project_name}_EXPORT
	EXPORT_FILE_NAME ${project_name}_Export.h
	STATIC_DEFINE ${project_name}_BUILT_AS_STATIC
)
