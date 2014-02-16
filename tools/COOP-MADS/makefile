EXE                 = coopmads.exe
COMPILATOR = mpic++
SUNAME = $(shell uname)
OSS=$(findstring MINGW32,$(SUNAME)) 
ifneq "$(strip $(OSS))" ""
COMPILATOR = g++
endif

COMPILATOR_OPTIONS  = -ansi -O2
L1                  = $(NOMAD_HOME)/lib/nomad.a
LIBS                = $(L1) -lm -lmpi
INCLUDE             = -I$(NOMAD_HOME)/src -I.
COMPILE             = $(COMPILATOR) $(COMPILATOR_OPTIONS) $(INCLUDE) -c
OBJS                = main.o Cache_Server.o

ifndef NOMAD_HOME
define ECHO_NOMAD
	@echo Please set NOMAD_HOME environment variable!
	@false
endef
endif

$(EXE): $(OBJS) $(L1)
	$(ECHO_NOMAD)
	$(COMPILATOR) -o $(EXE) $(OBJS) $(LIBS) $(COMPILATOR_OPTIONS)

main.o: main.cpp 
	$(COMPILE) main.cpp

Cache_Server.o: Cache_Server.cpp Cache_Server.hpp 
	$(ECHO_NOMAD)
	$(COMPILE) Cache_Server.cpp
	
$(L1): ;
	$(ECHO_NOMAD)	

clean:
	@echo "cleaning obj files"
	@rm -f $(OBJS)

del:
	@echo "cleaning trash files"
	@rm -f core *~
	@echo "cleaning obj files"
	@rm -f $(OBJS)
	@echo "cleaning exe file"
	@rm -f $(EXE)
