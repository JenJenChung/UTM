OBJS = UTMmain.o SimTypeNE.o SimNE.o ISimulator.o IDomainStateful.o IMultiagentSystem.o IAgent.o easymath.o easyio.o MultiagentNE.o IMultiagentSystem.o NeuroEvo.o NeuralNet.o MultiagentTypeNE.o TypeNeuroEvo.o NeuroEvoTypeWeighted.o NeuroEvoTypeCrossweighted.o ATFMSectorDomain.o AStarManager.o UAV.o Sector.o Fix.o
CC = g++ -std=c++11
DEBUG = -g
CFLAGS = -Wall -c $(DEBUG)
LFLAGS = -Wall $(DEBUG)
LIB = ../../libraries
DOMAINS =  $(LIB)/Domains
FILEIO = $(LIB)/FileIO
MATH = $(LIB)/Math
MULTI = $(LIB)/Multiagent
PLAN = $(LIB)/Planning
SIM = $(LIB)/Simulation
SINGLE = $(LIB)/SingleAgent
ATFM = $(DOMAINS)/ATFMSectorDomain
EASYIO = $(FILEIO)/easyio
NN = $(SINGLE)/NeuralNet
NE = $(SINGLE)/NeuroEvo

UTMmain : $(OBJS)
	$(CC) $(LFLAGS) $(OBJS) -o UTMmain

UTMmain.o : UTMmain.cpp $(SIM)/SimTypeNE.h $(ATFM)/ATFMSectorDomain.h
	$(CC) $(CFLAGS) UTMmain.cpp

SimTypeNE.o : $(SIM)/SimTypeNE.h $(SIM)/SimTypeNE.cpp $(SIM)/SimNE.h $(MULTI)/MultiagentTypeNE.h
	$(CC) $(CFLAGS) $(SIM)/SimTypeNE.cpp

SimNE.o : $(SIM)/SimNE.h $(SIM)/SimNE.cpp $(SIM)/ISimulator.h $(MULTI)/MultiagentNE.h $(MULTI)/IMultiagentSystem.h $(MATH)/easymath.h
	$(CC) $(CFLAGS) $(SIM)/SimNE.cpp

ISimulator.o : $(SIM)/ISimulator.h $(SIM)/ISimulator.cpp $(DOMAINS)/IDomainStateful.h $(MULTI)/IMultiagentSystem.h $(EASYIO)/easyio.h
	$(CC) $(CFLAGS) $(SIM)/ISimulator.cpp

IDomainStateful.o : $(DOMAINS)/IDomainStateful.h $(DOMAINS)/IDomainStateful.cpp
	$(CC) $(CFLAGS) $(DOMAINS)/IDomainStateful.cpp

IMultiagentSystem.o : $(MULTI)/IMultiagentSystem.h $(MULTI)/IMultiagentSystem.cpp $(SINGLE)/IAgent.h
	$(CC) $(CFLAGS) $(MULTI)/IMultiagentSystem.cpp

IAgent.o : $(SINGLE)/IAgent.h $(SINGLE)/IAgent.cpp $(MATH)/easymath.h
	$(CC) $(CFLAGS) $(SINGLE)/IAgent.cpp

easymath.o : $(MATH)/easymath.h $(MATH)/easymath.cpp
	$(CC) $(CFLAGS) $(MATH)/easymath.cpp

easyio.o : $(EASYIO)/easyio.h $(EASYIO)/easyio.cpp $(MATH)/Matrix.h
	$(CC) $(CFLAGS) $(EASYIO)/easyio.cpp

MultiagentNE.o : $(MULTI)/MultiagentNE.h $(MULTI)/MultiagentNE.cpp $(MULTI)/IMultiagentSystem.h $(NE)/NeuroEvo.h
	$(CC) $(CFLAGS) $(MULTI)/MultiagentNE.cpp

NeuroEvo.o : $(NE)/NeuroEvo.h $(NE)/NeuroEvo.cpp $(NN)/NeuralNet.h $(SINGLE)/IAgent.h
	$(CC) $(CFLAGS) $(NE)/NeuroEvo.cpp

NeuralNet.o : $(NN)/NeuralNet.h $(NN)/NeuralNet.cpp
	$(CC) $(CFLAGS) $(NN)/NeuralNet.cpp

MultiagentTypeNE.o : $(MULTI)/MultiagentTypeNE.h $(MULTI)/MultiagentTypeNE.cpp $(MULTI)/MultiagentNE.h $(NE)/TypeNeuroEvo.h $(NE)/NeuroEvo.h $(NE)/NeuroEvoTypeWeighted.h $(NE)/NeuroEvoTypeCrossweighted.h
	$(CC) $(CFLAGS) $(MULTI)/MultiagentTypeNE.cpp

TypeNeuroEvo.o : $(NE)/TypeNeuroEvo.h $(NE)/TypeNeuroEvo.cpp $(NE)/NeuroEvo.h $(MATH)/easymath.h $(SINGLE)/IAgent.h
	$(CC) $(CFLAGS) $(NE)/TypeNeuroEvo.cpp

NeuroEvoTypeWeighted.o : $(NE)/NeuroEvoTypeWeighted.h $(NE)/NeuroEvoTypeWeighted.cpp $(NE)/NeuroEvo.h $(NN)/TypeNeuralNet.h
	$(CC) $(CFLAGS) $(NE)/NeuroEvoTypeWeighted.cpp

NeuroEvoTypeCrossweighted.o : $(NE)/NeuroEvoTypeCrossweighted.h $(NE)/NeuroEvoTypeCrossweighted.cpp $(NE)/NeuroEvo.h $(NN)/TypeNeuralNet.h
	$(CC) $(CFLAGS) $(NE)/NeuroEvoTypeCrossweighted.cpp

ATFMSectorDomain.o : $(ATFM)/ATFMSectorDomain.h $(ATFM)/ATFMSectorDomain.cpp $(DOMAINS)/IDomainStateful.h $(MATH)/easymath.h $(EASYIO)/easyio.h $(PLAN)/AStarManager.h $(MATH)/Matrix.h $(ATFM)/UAV.h $(ATFM)/Sector.h $(ATFM)/Fix.h
	$(CC) $(CFLAGS) $(ATFM)/ATFMSectorDomain.cpp

AStarManager.o : $(PLAN)/AStarManager.h $(PLAN)/AStarManager.cpp $(PLAN)/AStar_easy.h $(PLAN)/AStar_grid.h $(MATH)/Matrix.h
	$(CC) $(CFLAGS) $(PLAN)/AStarManager.cpp

UAV.o : $(ATFM)/UAV.h $(ATFM)/UAV.cpp $(PLAN)/AStarManager.h $(MATH)/easymath.h $(MATH)/Matrix.h
	$(CC) $(CFLAGS) $(ATFM)/UAV.cpp

Sector.o : $(ATFM)/Sector.h $(ATFM)/Sector.cpp $(PLAN)/AStar_grid.h $(MATH)/Matrix.h
	$(CC) $(CFLAGS) $(ATFM)/Sector.cpp

Fix.o : $(ATFM)/Fix.h $(ATFM)/Fix.cpp $(ATFM)/UAV.h $(PLAN)/AStarManager.h
	$(CC) $(CFLAGS) $(ATFM)/Fix.cpp

clean:
	\rm *.o *~ UTMmain
