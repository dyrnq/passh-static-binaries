FROM alpine
RUN apk add --no-cache git clang musl-dev binutils curl
RUN curl -O https://raw.githubusercontent.com/clarkwang/passh/refs/heads/master/passh.c
RUN \
clang --verbose -std=c11 passh.c -c -o passh.o
RUN \
ld -o passh \
passh.o \
/usr/lib/crt1.o \
/usr/lib/crti.o \
/usr/lib/crtn.o \
-strip-all \
-static -L/usr/lib -L/lib -lc
RUN cp passh /usr/bin/passh
