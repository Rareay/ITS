add_library(its SHARED
        fun.cpp
        glad.c
        )

target_link_libraries(its
        ${THIRD_PARTY_LIBS})
