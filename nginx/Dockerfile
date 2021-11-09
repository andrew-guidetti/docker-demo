FROM ubuntu:18.04

MAINTAINER Andrew Guidetti <andrew.guidetti@gmail.com>

# install nginx repo and package
RUN apt-get update \
    && apt-get install -y software-properties-common \
    && apt-add-repository -y ppa:nginx/stable \
    && apt-get update \
    && apt-get install -y nginx

# clean up after apt-get update
RUN rm -rf /var/lib/apt/lists/*

# load in some configs? maybe later.
# ADD nginx/nginx.conf /etc/nginx/nginx.conf

# expose ports
EXPOSE 80 443

# fire up the ngin
CMD ["nginx", "-g", "daemon off;"]
