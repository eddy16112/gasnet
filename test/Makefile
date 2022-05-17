CC=mpicc
GASNET_ROOT=/scratch2/wwu/gasnet/GASNet-2022.3.0/install
INC_FLAGS=-I$(GASNET_ROOT)/include/ibv-conduit -I$(GASNET_ROOT)/include
CFLAGS=-D_GNU_SOURCE -DGASNET_PAR -D_REENTRANT
LD_FLAGS=-L$(GASNET_ROOT)/lib -lgasnet-ibv-par -libverbs -lcuda -lpthread
#DEBUG_FLAGS=-O2
DEBUG_FLAGS=-O0 -ggdb


gasnetex_testthreads: gasnetex_testthreads.c
	$(CC) -o $@ $< $(DEBUG_FLAGS) $(INC_FLAGS) $(CFLAGS) $(LD_FLAGS)

clean:
	rm gasnetex_testthreads
