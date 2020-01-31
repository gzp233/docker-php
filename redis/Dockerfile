FROM redis:latest

#RUN mkdir -p /usr/local/etc/redis
#COPY redis.conf /usr/local/etc/redis/redis.conf

VOLUME /data

RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone

#CMD ["redis-server", "/usr/local/etc/redis/redis.conf"]
CMD ["redis-server"]

EXPOSE 6379