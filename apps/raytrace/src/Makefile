TARGET = raytrace

OBJS = bbox.o cr.o env.o fbuf.o geo.o huprn.o husetup.o hutv.o isect.o \
	main.o matrix.o memory.o poly.o raystack.o shade.o sph.o trace.o \
	tri.o workpool.o
LDFLAGS = -lpthread -lm
MACROS = ../../../null_macros/c.m4.null.pthread
CFLAGS =  -O2 -w

x = *

# ifdef version
#   ifeq "$(version)" "IN_PARSEC"
#     PREFIX=${PARSECDIR}/ext/splash2/apps/${TARGET}/inst/${PARSECPLAT}
#     MACROS = ../../../../null_macros/c.m4.null.pthread
#   endif
# endif

raytrace: $(OBJS)
	gcc $(OBJS) $(CFLAGS) -o $(TARGET) $(LDFLAGS)


install:
	mkdir -p $(PREFIX)/bin
	cp -f $(TARGET) $(PREFIX)/bin/$(TARGET)
	cp -f run.sh $(PREFIX)/bin/run.sh

clean:
	rm -rf *.c *.h *.o $(TARGET)


M4 = m4 -Uindex -Ulen
RM = rm -f

.SUFFIXES:
.SUFFIXES:      .o .c .C .h .H

.H.h:
	$(M4) ${MACROS} $< > $@

.C.c:
	$(M4) $(MACROS) $< > $@

.c.o:
	gcc -c $(CFLAGS) $<

# .C.o:
# 	$(M4) $(MACROS) $*.C > $*.c
# 	gcc -c $(CFLAGS) $*.c

bbox.c: bbox.C rt.h
cr.c:	cr.C rt.h
env.c:	env.C rt.h
fbuf.c: fbuf.C rt.h
geo.c:	geo.C rt.h
huprn.c: huprn.C rt.h
husetup.c: husetup.C rt.h
hutv.c: hutv.C rt.h
isect.c: isect.C rt.h
main.c: main.C rt.h
matrix.c: matrix.C rt.h
memory.c: memory.C rt.h
poly.c: poly.C rt.h
raystack.c: raystack.C rt.h
shade.c: shade.C rt.h
sph.c:	sph.C rt.h
trace.c: trace.C rt.h
tri.c:	tri.C rt.h
workpool.c: workpool.C rt.h

# TEMP:
bbox.o: bbox.c
cr.o: cr.c
env.o: env.c
fbuf.o: fbuf.c
geo.o: geo.c
huprn.o: huprn.c
husetup.o: husetup.c
hutv.o: hutv.c
isect.o: isect.c
main.o: main.c
matrix.o: matrix.c
memory.o: memory.c
poly.o: poly.c
raystack.o: raystack.c
shade.o: shade.c
sph.o: sph.c
trace.o: trace.c
tri.o: tri.c
workpool.o: workpool.c

# bbox.c: bbox.C
# cr.c: cr.C
# env.c: env.C
# fbuf.c: fbuf.C
# geo.c: geo.C
# huprn.c: huprn.C
# husetup.c: husetup.C
# hutv.c: hutv.C
# isect.c: isect.C
# main.c: main.C
# matrix.c: matrix.C
# memory.c: memory.C
# poly.c: poly.C
# raystack.c: raystack.C
# shade.c: shade.C
# sph.c: sph.C
# trace.c: trace.C
# tri.c: tri.C
# workpool.c: workpool.C

rt.h: rt.H
