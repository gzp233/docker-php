FROM clickhouse/clickhouse-server:22.6

VOLUME /data

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone


EXPOSE 9009