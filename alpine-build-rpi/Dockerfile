FROM bhuisgen/rpi-alpine-build:latest
LABEL maintainer="Boris HUISGEN <bhuisgen@hbis.fr>"

COPY rootfs/ /

ENTRYPOINT [ "/usr/bin/qemu-arm-static", "-execve", "/bin/sh", "/usr/local/build/run.sh" ]
CMD []

WORKDIR /usr/local/build
