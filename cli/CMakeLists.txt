include_directories(${NOMAD_SOURCE_DIR}/libnomad)
link_directories(${NOMAD_BINARY_DIR}/libnomad)

add_executable(NOMAD nomad.cpp)

target_link_libraries(NOMAD nomad)

if(TGP)
	add_library(tgp SHARED IMPORTED)
	set_property(TARGET tgp PROPERTY IMPORTED_LOCATION $ENV{TGP_LIB})
	target_link_libraries(NOMAD tgp)
endif(TGP)

if(MPI)
	target_link_libraries(NOMAD ${MPI_LIBRARIES})
endif(MPI)

