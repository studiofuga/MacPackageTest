
add_library(B SHARED B.cpp B.h)

target_include_directories(B
        PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}
        )