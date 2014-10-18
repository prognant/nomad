cmake_minimum_required(VERSION 2.6)
project(NOMAD)

option(MPI "Build with MPI support" OFF)
if (MPI)
	find_package(MPI)
	include_directories(SYSTEM ${MPI_INCLUDE_PATH})
	set(CMAKE_CXX_COMPILE_FLAGS ${CMAKE_CXX_COMPILE_FLAGS} ${MPI_COMPILE_FLAGS} -DUSE_MPI)
	set(CMAKE_CXX_LINK_FLAGS ${CMAKE_CXX_LINK_FLAGS} ${MPI_LINK_FLAGS})
endif (MPI)
option(TGP "Build with TGP support" OFF)
if (TGP)
	# TODO: make it work
	include_directories($ENV{TGP_SRC})
	set(CMAKE_CXX_COMPILE_FLAGS ${CMAKE_CXX_COMPILE_FLAGS} -DUSE_TGP)
endif (TGP)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_COMPILE_FLAGS} -Wall")
add_subdirectory(libnomad)
add_subdirectory(cli)

