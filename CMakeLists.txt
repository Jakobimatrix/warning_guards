cmake_minimum_required (VERSION 3.0.2)
project(warning_guards)

add_library(${PROJECT_NAME} INTERFACE)
target_include_directories(${PROJECT_NAME} INTERFACE include/)

add_executable(basic_compilation_text test/basic_compilation_test.cpp)
target_link_libraries(basic_compilation_text ${PROJECT_NAME})
set_target_properties(basic_compilation_text PROPERTIES COMPILE_FLAGS "-Werror")

add_executable(oldstyle_cast_test test/oldstyle_cast_test.cpp)
target_link_libraries(oldstyle_cast_test ${PROJECT_NAME})
set_target_properties(oldstyle_cast_test PROPERTIES COMPILE_FLAGS "-Werror")

add_executable(register_test test/register_test.cpp)
target_link_libraries(register_test ${PROJECT_NAME})
set_target_properties(register_test PROPERTIES COMPILE_FLAGS "-Werror")

