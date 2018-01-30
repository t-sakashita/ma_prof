configure_file(config.h.in config.h COPYONLY)

set(LIB_SOURCES maprof.c maprof_proc.c maprof_time.c maprof_yaml.c mod_maprof.F90)
add_library(ma_prof_lib ${LIB_SOURCES})
target_include_directories(ma_prof_lib PRIVATE ${CMAKE_CURRENT_BINARY_DIR})
target_compile_definitions(ma_prof_lib PRIVATE "USE_MPI")
set_target_properties(ma_prof_lib PROPERTIES OUTPUT_NAME ma_prof)
