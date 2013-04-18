EXE                 = test.exe
COMPILATOR          = g++
FCOMPILATOR         = gfortran
COMPILATOR_OPTIONS  = -ansi -Wall -O3 
L1                  = $(NOMAD_HOME)/lib/nomad.a
LIBS                = $(L1) -lm
INCLUDE             = -I$(NOMAD_HOME)/src -I.
COMPILE             = $(COMPILATOR) $(COMPILATOR_OPTIONS) $(INCLUDE) -c
FCOMPILE            = $(FCOMPILATOR) -O3 -c
OBJS                = nomad.o test.o

ifndef NOMAD_HOME
define ECHO_NOMAD
	@echo Please set NOMAD_HOME environment variable!
	@false
endef
endif

$(EXE): $(L1) $(OBJS)
	$(ECHO_NOMAD)
	$(FCOMPILATOR) -o $(EXE) $(OBJS) $(LIBS) -lstdc++

nomad.o: nomad.cpp
	$(COMPILE) nomad.cpp

test.o: test.f
	$(FCOMPILE) test.f

$(L1): ;
	$(ECHO_NOMAD)
	
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
