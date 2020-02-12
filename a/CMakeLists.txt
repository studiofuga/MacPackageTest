
add_library(A SHARED A.cpp A.h)

target_include_directories(A
        PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}
        )

