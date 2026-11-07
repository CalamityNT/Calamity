project(explorer)

list(APPEND SOURCE
    appbar.c
    desktop.c
    explorer.c
    startmenu.c
    systray.c)

add_executable(explorer ${SOURCE} explorer.rc)
target_include_directories(explorer PRIVATE
    ${REACTOS_SOURCE_DIR}/win32ss/include)
set_module_type(explorer win32gui UNICODE)
add_importlibs(explorer rpcrt4 user32 gdi32 advapi32 win32u comctl32 shell32 oleaut32 ole32 shlwapi msvcrt kernel32 ntdll)
target_link_libraries(explorer wine)
add_dependencies(explorer psdk)
add_cd_file(TARGET explorer DESTINATION reactos FOR all)
