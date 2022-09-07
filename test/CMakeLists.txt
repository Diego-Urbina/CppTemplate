include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG release-1.12.1
)
FetchContent_MakeAvailable(googletest)
add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest_main)

add_executable(
  ProjectTest
  main_test.cpp
)
target_link_libraries(
  ProjectTest
  GTest::gtest_main
)
target_link_libraries(
    ProjectTest
    ${CONAN_LIBS}
)

include(GoogleTest)
gtest_discover_tests(ProjectTest)