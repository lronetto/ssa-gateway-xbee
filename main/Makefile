TARGET = ssa_main
LIBS = -lm -lssl -lcrypto
CC = gcc
CFLAGS = -g -O3 

.PHONY: default all clean

default: $(TARGET)
all: default

INC=-I../include

SRC = ../lib/serial.c ../lib/xbee.c ../lib/ssl.c $(wildcard *.c)
OBJ= $(SRC:.c=.o)

%.o: %.c  
	$(CC) $(CFLAGS) $(INC) -c $< -o $@ 

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJ)
	$(CC) $(OBJ) $(LIBS) $(INC) -o $@

teste:
	echo $(SRC)
	echo $(OBJ)

cpp:
	cppcheck /home/ssa/*
	
clean:
	-rm -f *.o
	-rm -f ../lib/*.o
	-rm -f $(TARGET)
