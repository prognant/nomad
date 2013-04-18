EXE                 = cache_inspect
COMPILATOR          = g++
COMPILATOR_OPTIONS  = -ansi -Wall -O2
L1                  = $(NOMAD_HOME)/lib/nomad.a
LIBS                = $(L1) -lc -lm
INCLUDE             = -I$(NOMAD_HOME)/src -I.
COMPILE             = $(COMPILATOR) $(COMPILATOR_OPTIONS) $(INCLUDE) -c
OBJS                = cache_inspect.o

$(EXE): $(OBJS)
	$(COMPILATOR) -o $(EXE) $(OBJS) $(LIBS) $(COMPILATOR_OPTIONS)

cache_inspect.o: cache_inspect.cpp $(L1)
	$(COMPILE) cache_inspect.cpp

mpi: COMPILATOR          = mpic++
mpi: EXE                 = cache_inspect_MPI
mpi: L1                  = $(NOMAD_HOME)/lib/nomad.MPI.a
mpi: LIBS                = $(L1) -lc -lm
mpi: COMPILATOR_OPTIONS += -DUSE_MPI
mpi: clean $(OBJS)
	@echo "   building the MPI version ..."
	@echo "   exe file : "$(EXE)
	@$(COMPILATOR) -o  $(EXE) $(OBJS) $(LIBS) $(COMPILATOR_OPTIONS)
	@strip  $(EXE)

clean:
	@echo "   cleaning obj files"
	@rm -f $(OBJS)

del:
	@echo "   cleaning trash files"
	@rm -f core *~
	@echo "   cleaning obj files"
	@rm -f $(OBJS)
	@echo "   cleaning exe file"
	@rm -f $(EXE)
