CC=gcc
CFLAGS=-Wall -O3

all: limmat

limmat: limmat.h main.c liblimmat.a
	$(CC) $(CFLAGS) -o $@ main.c -L. -llimmat
liblimmat.a: limmat.o
	ar rc $@ limmat.o
	ranlib $@
limmat.o: limmat.c limmat.h config.h
	$(CC) $(CFLAGS) -c -o $@ limmat.c
white: limmat.h limmat.c config.h
	$(CC) $(CFLAGS) -DLIMMAT_WHITE -o $@ limmat.c
clean:
	rm -f log/*.log *.o
	rm -f *~ tags core
	rm -f white liblimmat.a 
clean-all: clean
	rm -f limmat 	
distclean: clean-all
	rm -f config.h Makefile

.PHONY: all clean-all distclean export
