PREFIX ?= $(DESTDIR)/usr/local
BINDIR = $(PREFIX)/bin

PROG = pskracker
SRCS = pskracker.c
OBJS = $(SRCS:.c=.o)

CFLAGS += -Wno-unused -Wno-return-type

all: $(PROG)

install:
	install -m 755 $(PROG) $(BINDIR)/$(PROG)

clean:
	$(RM) $(PROG)
	$(RM) $(OBJS)

%.o: %.c
	$(CC) $(CFLAGS) $(PIC) -c -o $@ $<

$(PROG): $(OBJS)
	$(CC) $(LDFLAGS) $(OBJS) $(LIBS) -o $@

.PHONY: all clean install
