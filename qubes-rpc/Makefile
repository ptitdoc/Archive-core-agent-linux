CC=gcc
CFLAGS=-g -Wall -I. -fPIC -pie
all:	vm-file-editor qopen-in-vm qfile-unpacker tar2qfile
vm-file-editor: vm-file-editor.o ioall.o
	$(CC) -pie -g -o $@ $^
qopen-in-vm: qopen-in-vm.o ioall.o gui-fatal.o
	$(CC) -pie -g -o $@ $^
qfile-agent: qfile-agent.o gui-fatal.o qfile-utils.o
	$(CC) -pie -g -o $@ $^ -lqubes-rpc-filecopy
qfile-unpacker: qfile-unpacker.o gui-fatal.o
	$(CC) -pie -g -o $@ $^ -lqubes-rpc-filecopy
tar2qfile: qfile-utils.o tar2qfile.o gui-fatal.o
	$(CC) -pie -g -o $@ $^ -lqubes-rpc-filecopy

clean:
	rm -f qopen-in-vm qfile-agent qfile-unpacker tar2qfile vm-file-editor *.o *~
