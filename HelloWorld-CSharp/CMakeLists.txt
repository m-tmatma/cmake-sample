cmake_minimum_required(VERSION 3.10.1)
set(CMAKE_SUPPRESS_REGENERATION true)

# define a variable of project name
set(project_name "HelloWorld-CSharp")

# define a project name
project (${project_name})

enable_language(CSharp)

# define a variable SRC with file GLOB
file(GLOB SRC *.cs)

add_executable(${project_name} ${SRC})

set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT ${project_name})

