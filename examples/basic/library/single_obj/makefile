EXE                 = basic_lib.exe
EXE_MPI				= basic_lib_MPI.exe

COMPILATOR          = g++
COMPILATOR_MPI = mpic++
SUNAME = $(shell uname)
OSS=$(findstring MINGW32,$(SUNAME)) 
ifneq "$(strip $(OSS))" ""
COMPILATOR_MPI = g++
endif

COMPILATOR_OPTIONS  = -O2 -ansi 
COMPILATOR_OPTIONS_MPI = $(COMPILATOR_OPTIONS) -DUSE_MPI
L1                  = $(NOMAD_HOME)/lib/nomad.a
L1_MPI				= $(NOMAD_HOME)/lib/nomad.MPI.a
LIBS                = $(L1) -lm
LIBS_MPI			= $(L1_MPI) -lm -lmpi
INCLUDE             = -I$(NOMAD_HOME)/src -I.
COMPILE             = $(COMPILATOR) $(COMPILATOR_OPTIONS) $(INCLUDE) -c
COMPILE_MPI			= $(COMPILATOR_MPI) $(COMPILATOR_OPTIONS_MPI) $(INCLUDE) -c
OBJS                = basic_lib.o
OBJS_MPI            = basic_lib_MPI.o


ifndef NOMAD_HOME
define ECHO_NOMAD
	@echo Please set NOMAD_HOME environment variable!
	@false
endef
endif


$(EXE): $(L1) $(OBJS)
	$(ECHO_NOMAD)
	@echo "   building the scalar version ..."
	@echo "   exe file : "$(EXE)
	@$(COMPILATOR) -o  $(EXE) $(OBJS) $(LIBS) $(COMPILATOR_OPTIONS)
	@strip  $(EXE)

$(EXE_MPI): $(L1_MPI) $(OBJS_MPI) 
	$(ECHO_NOMAD)
	@echo "   building the MPI version ..."
	@echo "   exe file : "$(EXE_MPI)
	@$(COMPILATOR_MPI) -o  $(EXE_MPI) $(OBJS_MPI) $(LIBS_MPI) $(COMPILATOR_OPTIONS_MPI)
	@strip  $(EXE_MPI)

basic_lib.o: basic_lib.cpp
	$(ECHO_NOMAD)
	@$(COMPILE) basic_lib.cpp

basic_lib_MPI.o: basic_lib.cpp 
	$(ECHO_NOMAD)
	@$(COMPILE_MPI) basic_lib.cpp -o basic_lib_MPI.o

$(L1) $(L1_MPI): ;
	$(ECHO_NOMAD)

mpi: $(EXE_MPI)

all: $(EXE) $(EXE_MPI)

clean: ;
	@echo "   cleaning obj files"
	@rm -f $(OBJS) $(OBJS_MPI)

del: ;
	@echo "   cleaning trash files"
	@rm -f core *~
	@echo "   cleaning obj files"
	@rm -f $(OBJS) $(OBJS_MPI)
	@echo "   cleaning exe file"
	@rm -f $(EXE) $(EXE_MPI)


