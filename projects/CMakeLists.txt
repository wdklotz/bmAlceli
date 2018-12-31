cmake_minimum_required(VERSION $ENV{ACC_CMAKE_VERSION})

set(INC_DIRS
)

set (SRC_DIRS
)

#OpenMP Flags
#set (FFLAGS "-openmp")
#set (LINK_FLAGS "-openmp")

set (EXE_SPECS
  cmake.simple_bmad_program
)

# Only build mpi_mp if both ACC_ENABLE_OPENMP and ACC_ENABLE_MPI are set to "Y".

if ($ENV{ACC_ENABLE_OPENMP} AND $ENV{ACC_ENABLE_MPI})
  list (APPEND EXE_SPECS "cmake.mpi_mp")
endif ()


include($ENV{ACC_BUILD_SYSTEM}/Master.cmake)
