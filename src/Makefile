LIBNAME = libfeatures.so
SOURCES = array.c sift.c ransac.c register.c dog.c harris.c
OBJECTS = $(SOURCES:.c=.o)

CC = gcc
CFLAGS = -c -Wall -fPIC `pkg-config --cflags opencv`
LDFLAGS = -lm -shared -Wl,-soname,$LIBNAME

all: $(LIBNAME)

$(LIBNAME): $(OBJECTS)
	$(CC) $(LDFLAGS) `pkg-config --libs opencv` $(OBJECTS) -o $(LIBNAME)
	mv $(LIBNAME) ..

.c.o:
	$(CC) $(CFLAGS) $< -o $@

clean:
	rm -rf $(OBJECTS) $(LIBNAME)
