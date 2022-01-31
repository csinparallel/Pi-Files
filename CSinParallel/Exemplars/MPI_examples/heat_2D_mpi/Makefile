MPI_CC  = mpicc
CC      = gcc
CFLAGS  = -ansi -pedantic -std=c99 -Wno-unused-result -Wno-format-overflow -Wno-maybe-unitialized

# source files for larger dynamically sized plates
SRCS1      = mpi_heat2D_big.c display.c gnuplot_i.c
# object files from source files
OBJS1      = $(SRCS1:.c=.o)

# source files for small hard-coded size of plate and number of iterations
SRCS2      = mpi_heat2D.c display.c gnuplot_i.c
# object files from source files
OBJS2      = $(SRCS2:.c=.o)


PROGS = heat2D_big heat2D_small seq_heat2D

all: small big seq

# valid file suffixes 
.SUFFIXES: .c .o .cpp

# command to build .o files from .c files
.c.o: 
	$(MPI_CC) -c $(CFLAGS) $<

small: $(OBJS2)
	$(MPI_CC) $(CFLAGS) -o heat2D_small $(OBJS2)

big: $(OBJS1)
	$(MPI_CC) $(CFLAGS) -o heat2D_big $(OBJS1)

seq: seq_heat2D.c seq_time.h
	$(CC) $(CFLAGS) -o seq_heat2D seq_heat2D.c

clean:
	/bin/rm -f *.o $(PROGS) initial.dat final.dat *~ *# a.out