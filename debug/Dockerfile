FROM alpine:edge
RUN apk update && apk add strace libcap-ng  lsof  gdb ltrace sysstat
CMD ["strace", "-p", "1"]