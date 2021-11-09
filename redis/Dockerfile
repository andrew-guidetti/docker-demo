FROM ubuntu:18.04

MAINTAINER Andrew Guidetti <andrew.guidetti@gmail.com>

# install redis repo and package
RUN apt-get update \
    && apt-get install -y software-properties-common \
    && apt-add-repository -y ppa:redislabs/redis \
    && apt-get update \
    && apt-get install -y redis

# clean up after apt-get update
RUN rm -rf /var/lib/apt/lists/*

# load in some configs? maybe later.
# ADD redis/redis.conf /redis.conf

# expose port
EXPOSE 6379

# start the server in unsecure mode!!
CMD ["redis-server","--protected-mode no"]

# start the server with a config?
# CMD ["redis-server","/redis.conf"]
