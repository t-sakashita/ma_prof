configure_file(config.h.in config.h COPYONLY)

set(CMAKE_C_FLAGS "-DUSE_MPI")
set(CMAKE_Fortran_FLAGS "-DUSE_MPI")

#include_directories(${CURRENT_SOURCE_DIR}/src)
#include_directories(${CMAKE_CURRENT_BINARY_DIR})

set(LIB_SOURCES maprof.c maprof_proc.c maprof_time.c maprof_yaml.c mod_maprof.F90)
add_library(ma_prof_lib ${LIB_SOURCES})
target_include_directories(ma_prof_lib PRIVATE ${CMAKE_CURRENT_BINARY_DIR})
set_target_properties(ma_prof_lib PROPERTIES OUTPUT_NAME ma_prof)
