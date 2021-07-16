FROM yandex/clickhouse-server:latest

VOLUME /data

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone


EXPOSE 9009