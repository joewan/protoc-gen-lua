SRC=pb.c

TARGET=pb.so
CFLAGS=-I/usr/local/include -I/usr/include -std=gnu99 -D_ALLBSD_SOURCE
LDFLAGS=-L/usr/local/lib -llua

all:$(TARGET)

$(TARGET):$(SRC)
	gcc -O3 -shared -fPIC $(SRC) $(CFLAGS) $(LDFLAGS) -o $@
