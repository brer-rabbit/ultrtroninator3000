TARGET = 808_X0X_909
INCLUDE = -I../../include
LIBS = -li2c -lconfig -lpulse -lsndfile -lpthread  -L../../lib/ -lut3k
CC = gcc
#CFLAGS = -g -Wall
CFLAGS = -O2 -Wall

.PHONY: default all clean

default: $(TARGET)
all: default

OBJECTS = $(patsubst %.c, %.o, $(wildcard *.c))
HEADERS = $(wildcard *.h)

%.o: %.c $(HEADERS)
	$(CC) $(INCLUDE) $(CFLAGS) -c $< -o $@

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	$(CC) $(OBJECTS) -Wall $(LIBS) -o $@

clean:
	-rm -f *.o
	-rm -f $(TARGET)

