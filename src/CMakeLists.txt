
set(APP_NAME MacPackageTest)

add_executable(${APP_NAME} MACOSX_BUNDLE main.cpp)

target_include_directories(MacPackageTest
        PRIVATE
        $<TARGET_PROPERTY:A,INTERFACE_INCLUDE_DIRECTORIES>
        $<TARGET_PROPERTY:B,INTERFACE_INCLUDE_DIRECTORIES>
        )

target_link_libraries(MacPackageTest A B)


# Destination paths below are relative to ${CMAKE_INSTALL_PREFIX}
install(TARGETS ${APP_NAME}
        BUNDLE DESTINATION . COMPONENT Runtime
        RUNTIME DESTINATION bin COMPONENT Runtime
        )

# Note Mac specific extension .app
set(APPS "\${CMAKE_INSTALL_PREFIX}/${APP_NAME}.app")

# Directories to look for dependencies
set(DIRS ${CMAKE_BINARY_DIR}/bin )

install(CODE "include(BundleUtilities)
    fixup_bundle(\"${APPS}\" \"\" \"${DIRS}\")")

set(CPACK_GENERATOR "DragNDrop")
include(CPack)