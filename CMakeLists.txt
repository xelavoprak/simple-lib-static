cmake_minimum_required(VERSION 3.10)

project(simple-lib-static)

add_library(${PROJECT_NAME} STATIC
	src/simple.cpp
)


target_include_directories(${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/include
)

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 11)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD_REQUIRED ON)


add_executable(hello_binary src/main.cpp)


target_link_libraries( hello_binary
    PRIVATE ${PROJECT_NAME}
)