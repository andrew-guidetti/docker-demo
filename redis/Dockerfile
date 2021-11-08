MAINTAINER Andrew Guidetti <andrew.guidetti@gmail.com>

FROM ubuntu:18.04

#Install Redis repo and package
RUN apt-get update \
    && apt-get install -y software-properties-common \
    && apt-add-repository -y ppa:redislabs/redis \
    && apt-get update
    && apt-get install -y redis

# Clean up after apt-get update
RUN rm -rf /var/lib/apt/lists/*

# load in some configs?
# ADD redis/redis.conf /redis.conf

# log the logs
RUN ln -sf /dev/stdout /var/log/redis/redis-server.log

# Expose port
EXPOSE 6379

# start the server
CMD ["redis-server"]

# start the server with a config
# CMD ["redis-server","/redis.conf"]
