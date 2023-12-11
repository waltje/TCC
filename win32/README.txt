Starting with the 0.28rc release, we _always_ use the architecture
prefix to locate any support files (libtcc1.a, etc) so we can use
a single 'lib' directory for all supported platforms:

  i386-win32-bcheck.o
  i386-win32-bt-dll.o
  i386-win32-bt-exe.o
  i386-win32-bt-log.o
  i386-win32-libtcc1.a
  x86_64-win32-bcheck.o
  x86_64-win32-bt-dll.o
  x86_64-win32-bt-exe.o
  x86_64-win32-bt-log.o
  x86_64-win32-libtcc1.a

and the generic ones for the system libraries:

  msvcrt.def
  kernel32.def
  user32.def
  gdi32.def
  winmm.def
  ws2_32.def

This may have to change later, as several system libraries have
changed between various releases (and architectures) of the Windows
system, and, therefore, separate .def's for those files would be
needed.
