project(explorer)

list(APPEND SOURCE
    appbar.c
    desktop.c
    explorer.c
    startmenu.c
    systray.c)

add_executable(explorer ${SOURCE} explorer.rc)
set_module_type(explorer win32gui UNICODE)
add_importlibs(explorer rpcrt4 user32 gdi32 advapi32 win32u comctl32 shell32 oleaut32 ole32 shlwapi msvcrt kernel32 ntdll)
add_cd_file(TARGET explorer DESTINATION reactos FOR all)
