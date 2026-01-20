FROM alpine as build
ARG version=v1.0.2
RUN apk add --no-cache git clang musl-dev binutils curl
RUN curl -O https://raw.githubusercontent.com/clarkwang/passh/refs/tags/${version}/passh.c
RUN \
clang --verbose -std=c11 passh.c -c -o passh.o
RUN \
ld -o passh \
passh.o \
/usr/lib/crt1.o \
/usr/lib/crti.o \
/usr/lib/crtn.o \
-strip-all \
-static -L/usr/lib -L/lib -lc -lm
RUN cp passh /usr/bin/passh

FROM alpine

COPY --from=build /usr/bin/passh /usr/bin
