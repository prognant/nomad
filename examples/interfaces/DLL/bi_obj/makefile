EXE                 = nomad_for_dll.exe
COMPILATOR          = g++
COMPILATOR_OPTIONS  = -O3
L1                  = $(NOMAD_HOME)/lib/nomad.a
LIBS                = $(L1) -lm
INCLUDE             = -I$(NOMAD_HOME)/src -I.
COMPILE             = $(COMPILATOR) $(COMPILATOR_OPTIONS) $(INCLUDE) -c
OBJS                = nomad_for_dll.o

ifndef NOMAD_HOME
define ECHO_NOMAD
	@echo Please set NOMAD_HOME environment variable!
	@false
endef
endif

$(EXE): $(L1) $(OBJS)
	$(ECHO_NOMAD)
	$(COMPILATOR) -o $(EXE) $(OBJS) $(LIBS) $(COMPILATOR_OPTIONS)

nomad_for_dll.o: nomad_for_dll.cpp $(L1)
	$(ECHO_NOMAD)
	$(COMPILE) nomad_for_dll.cpp

$(L1): ;
	$(ECHO_NOMAD)

clean:
	@echo cleaning obj files
	@del $(OBJS)

del:
	@echo cleaning obj files
	@del $(OBJS)
	@echo cleaning exe file
	@del $(EXE)
