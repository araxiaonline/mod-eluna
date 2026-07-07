# Defines the `lualib` static library target consumed by the core's ALE module
# handling (modules/CMakeLists.txt links `modules` against `lualib` and excludes
# lua.c/luac.c from the module source glob). The core auto-includes any
# modules/<name>/CMakeLists.txt from its top-level CMakeLists.
# This file is processed before the core loads its macro set (top-level
# CMakeLists includes module dirs at line ~72, AutoCollect at ~103), so pull
# in the macros lualib's CMakeLists needs. CMAKE_MODULE_PATH already points
# at src/cmake/macros by then; re-inclusion later is harmless.
include(AutoCollect)
add_subdirectory(src/lualib)
