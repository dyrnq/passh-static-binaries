FROM alpine as build
ARG version=v1.0.2
RUN apk add --no-cache git musl-dev musl-dev binutils curl build-base
RUN curl -O https://raw.githubusercontent.com/clarkwang/passh/refs/tags/${version}/passh.c
RUN musl-gcc -static -O2 passh.c -o passh
RUN cp passh /usr/bin/passh

FROM alpine

COPY --from=build /usr/bin/passh /usr/bin
