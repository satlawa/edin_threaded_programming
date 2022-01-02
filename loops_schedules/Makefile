# Makefile for mandelbrot area code

#
# C compiler and options for Intel
#
#CC=     icc -O3 -qopenmp -std=c99
#LIB=    -lm

#
# C compiler and options for PGI
#
#CC=     pgcc -O3 -mp -tp=px
#LIB=	-lm

###############
# C compiler and options for GNU
###############
CC=     gcc -O3 -fopenmp
LIB=	-lm

###############
# Object files
###############
OBJ=    loop_schedules.o

###############
# Compile
###############
loop_schedules:   $(OBJ)
	$(CC) -o $@ $(OBJ) $(LIB)

.c.o:
	$(CC) -c $<

#
# Clean out object files and the executable.
#
clean:
	rm *.o loop_schedules
