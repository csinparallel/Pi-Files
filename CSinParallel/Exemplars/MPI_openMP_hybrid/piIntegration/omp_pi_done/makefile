OBJ = omp_pi_done

CC = gcc
CFLAGS = -Wall -ansi -pedantic -std=c99
LFLAGS = -o $(OBJ) -fopenmp

$(OBJ): $(OBJ).c
	$(CC) $(CFLAGS) $(OBJ).c $(LFLAGS)

clean:
	rm -f a.out $(OBJ)
