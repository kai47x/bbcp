# This is GNU Makefile
#    BSD       GNU
# ${.TARGET}    $@
# ${.ALLSRC}    $^
# ${.IMPSRC}    $<

INCDIR ?= /usr/include

all: Termios.odc

Termios.odc: Termios.txt
	./txt2odc.py Termios.txt Termios.odc

PY = python2.7
DEFS = defs-termios

Termios.txt: Termios.txt.templ ${DEFS}
	${PY} ./untempl.py Termios.txt.templ $@

defs-termios:
	./dumpdefs.py 2 0 i ${INCDIR}/i386-linux-gnu/bits/termios.h > $@

clean:
	rm -f Termios.txt Termios.odc ${DEFS}
