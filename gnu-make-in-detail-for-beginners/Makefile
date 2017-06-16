CC := gcc
#conditional
CC ?= hoge
#appending
CC += -W
FUGA ?= fuga

#Use PHONY to specify which targets are not to be treates as files
.PHONY: all clean

#assignment command output
LS_OUT = $(shell ls)

all: main.o module.o
	CC main.o module.o -o target_bin
main.o: main.c module.h
	CC -I . -c main.c
module.o: module.c module.h
	CC -I . -c module.c
clean:
	rm -rf *.o
	rm target_bin

%_exists: %
	echo $* "exists"
echo_cc:
	echo ${CC}
echo_fuga:
	echo ${FUGA}
echo_ls:
	echo ${LS_OUT}
dump_vars: module.c module.o
	echo 'target name is ' $@
	echo 'new dependencies are '$?

ignore_error:
	-cat fugahoge.txt
	-echo "ignore error"

suppress_stdout:
	@ls -l
