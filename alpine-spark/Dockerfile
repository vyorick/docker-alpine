FROM bhuisgen/alpine-base-consul:latest
LABEL maintainer="Boris HUISGEN <bhuisgen@hbis.fr>"

ENV SPARK_VERSION=2.2.1 \
    HADOOP_VERSION=2.7 \
    SPARK_HOME=/usr/local/spark

RUN mkdir ${SPARK_HOME} && \
    addgroup -S spark && \
    adduser -S -D -g "" -G spark -s /bin/sh -h ${SPARK_HOME} spark && \
    chown spark:spark ${SPARK_HOME}

RUN apk add --update openjdk8-jre tar && \
    curl -sSL http://apache.mirrors.ovh.net/ftp.apache.org/dist/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz | \
        tar -xzo -C ${SPARK_HOME} --strip-components 1 && \
    apk del tar && \
    rm -rf /var/cache/apk/*

COPY rootfs/ /

ENTRYPOINT ["/init"]
CMD []
