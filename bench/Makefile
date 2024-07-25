CC=riscv64-unknown-linux-gnu-gcc
CXX=riscv64-unknown-linux-gnu-g++
PGMS=latency latency-mlp bandwidth pagetype bandwidth-rt

CFLAGS=-O2 -Wall -g
CXXFLAGS=$(CFLAGS)
LDFLAGS=-Wl,--no-as-needed -lrt

build:
	mkdir build

all: $(PGMS)
	mkdir build
	mv latency build/
	mv latency-mlp build/
	mv bandwidth build/
	mv bandwidth-rt build/
	mv pagetype build/
	

latency: latency.o
latency-mlp: latency-mlp.o
	$(CXX) $(CFLAGS) $(LDFLAGS) $< -o $@
bandwidth: bandwidth.o
bandwidth-rt: bandwidth-rt.o
	$(CC) $(CFLAGS) $(LDFLAGS) $< -o $@ -lpthread
pagetype: pagetype.o

install:
	cp -v $(PGMS) /usr/local/bin
clean:
	rm *.o *~ $(PGMS)
