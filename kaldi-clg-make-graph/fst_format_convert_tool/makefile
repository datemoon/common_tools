
CXXFLAGS=-msse -msse2 -Wall -I.. -pthread \
		 -O3 -DNDEBUG  #-std=c++0x #-gdwarf-2 #-gstabs+ #-DDEBUGTOKEN -g #-pg #-DDEBUG #-DDEBUGGRAPH

CXXFLAGS += -fPIC

LDFLAGS = -rdynamic

LDLIBS = -lm -lpthread -ldl

GCC=gcc
CC = g++
CXX = g++
GXX = g++
AR = ar
AS = as
RANLIB = ranlib

BIN=convert_fst convert_hmm

all:$(BIN)

convert_fst:read_fst.o convert_fst.o write_fst.o
	$(GCC) $(CFLAGS) -o $@ $^

convert_hmm:convert_hmm.o read_fst.o write_fst.o
	$(GCC) $(CFLAGS) -o $@ $^

%.o:%.c
	$(GCC) $(CFLAGS) -c $^

.PHONY:clean

clean:
	rm -f *.o $(BIN)
