SET(TEST_SOURCES test1)

FOREACH (test_src ${TEST_SOURCES})
    ADD_EXECUTABLE(${test_src} ${test_src}.cpp)
    TARGET_LINK_LIBRARIES(${test_src} ${THIRD_PARTY_LIBS} its)
    ADD_TEST(${test_src} ${test_src})
ENDFOREACH (test_src)
