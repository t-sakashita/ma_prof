configure_file(config.h.in config.h COPYONLY)

set(CMAKE_C_FLAGS "-DUSE_MPI")
set(CMAKE_Fortran_FLAGS "-DUSE_MPI")

set(LIB_SOURCES maprof.c maprof_proc.c maprof_time.c maprof_yaml.c mod_maprof.F90)
add_library(ma_prof_lib ${LIB_SOURCES})
set_target_properties(ma_prof_lib PROPERTIES OUTPUT_NAME ma_prof)
