add_executable(
    ProjectTest
    main_test.cpp
)

target_link_libraries(
    ProjectTest
    ${CONAN_LIBS}
)

include(GoogleTest)
gtest_discover_tests(ProjectTest)
