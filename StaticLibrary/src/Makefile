CC ?= gcc
#time
CT := "\"`date '+%Y-%m-%d %H:%M:%S'`"\"
#编译器选项
CFLAGS  := -g -Wall
#展开通通配符
SRCS := $(wildcard ./src/*.c)
#所有的c文件换成o
COBJS := $(patsubst %.c,%.o,$(SRCS))
#依赖的头文件
INCDIR  := -I../include

TARGET  := helloworld.a

all:$(COBJS)
		ar cr $(TARGET) $(COBJS)
			@rm -rf $(COBJS)

.SUFFIXES: .c .o
	.c.o:
		$(CC) $(CFLAGS) $(INCDIR) -c $*.c -o $*.o -DCT=$(CT)

.PHONY:clean
	clean:
		rm -rf $(COBJS) $(TARGET)

