find_package(PkgConfig REQUIRED)

pkg_check_modules(LIBINPUT REQUIRED IMPORTED_TARGET libinput)
pkg_check_modules(LIBUDEV  REQUIRED IMPORTED_TARGET libudev)

add_executable(lotus-vibe-server lotus-server.cpp lotus-logger.cpp)

target_link_libraries(lotus-vibe-server
    PkgConfig::LIBINPUT
    PkgConfig::LIBUDEV
)

install(TARGETS lotus-vibe-server DESTINATION ${CMAKE_INSTALL_BINDIR})
