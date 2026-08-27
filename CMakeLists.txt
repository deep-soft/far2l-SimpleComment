project(SimpleComment)

set(SOURCES
src/SimpleComment.cpp
)

add_library (SimpleComment MODULE ${SOURCES})

target_link_libraries(SimpleComment utils far2l)

target_compile_definitions(SimpleComment PRIVATE -DWINPORT_DIRECT -DUNICODE -DFAR_DONT_USE_INTERNALS)

target_include_directories(SimpleComment PRIVATE .)
target_include_directories(SimpleComment PRIVATE ${CMAKE_SOURCE_DIR}/WinPort)
target_include_directories(SimpleComment PRIVATE ${CMAKE_SOURCE_DIR}/far2l/far2sdk)

set_target_properties(SimpleComment
    PROPERTIES
        LIBRARY_OUTPUT_DIRECTORY "${INSTALL_DIR}/Plugins/SimpleComment/plug"
        PREFIX ""
        SUFFIX ".far-plug-wide")
