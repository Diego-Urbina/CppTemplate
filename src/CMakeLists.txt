add_executable(
    Project 
    main.cpp
)

target_link_libraries(
    Project
    ${CONAN_LIBS}
)
