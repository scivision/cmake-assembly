cmake_minimum_required(VERSION 3.15)

project(assemblyOut LANGUAGES C Fortran)

# --- auto-ignore build directory
if(NOT EXISTS ${PROJECT_BINARY_DIR}/.gitignore)
  file(WRITE ${PROJECT_BINARY_DIR}/.gitignore "*")
endif()

include(asm.cmake)

c2asm(c_multiply c_multiply.c)
c2asm(c_power c_power.c)
f2asm(f_multiply f_multiply.f90)
