cmake_minimum_required(VERSION 3.0)
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")
find_package(Foo REQUIRED) # FOO_INCLUDE_DIR, FOO_LIBRARIES
find_package(Boo CONFIG REQUIRED)

include_directories("${FOO_INCLUDE_DIR}")
add_executable(Bar Bar.cpp)
add_dependencies(Bar Foo)
target_link_libraries(Bar ${FOO_LIBRARIES} Boo::Boo)
