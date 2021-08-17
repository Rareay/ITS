add_library(its SHARED
        fun.cpp
        )

target_link_libraries(its
        ${THIRD_PARTY_LIBS})
