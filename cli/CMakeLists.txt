include_directories(${NOMAD_SOURCE_DIR}/libnomad)
link_directories(${NOMAD_BINARY_DIR}/libnomad)

add_executable(NOMAD nomad.cpp)
target_link_libraries(NOMAD nomad ${MPI_LIBRARIES})

