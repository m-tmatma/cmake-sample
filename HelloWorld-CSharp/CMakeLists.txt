cmake_minimum_required(VERSION 3.8)

# define a variable of project name
set( project_name "HelloWorld-CSharp")

enable_language(CSharp)

# set the project as the startup project
set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT ${project_name} )

# define a project name
project (${project_name})

# define a variable SRC with file GLOB
file(GLOB SRC *.cs)

# define sources files of an executable
add_executable(${project_name} ${SRC})
