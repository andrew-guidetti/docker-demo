MAINTAINER Andrew Guidetti <andrew.guidetti@gmail.com>

FROM ubuntu:18.04

#Install Nginx repo and package
RUN apt-get update \
    && apt-get install -y software-properties-common \
    && apt-add-repository -y ppa:nginx/stable \
    && apt-get update \
    && apt-get install -y nginx

# Clean up after apt-get update
RUN rm -rf /var/lib/apt/lists/*

# Add some configs?
# ADD nginx/nginx.conf /etc/nginx/nginx.conf

# log the logs
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

# Expose the ports
EXPOSE 80 443

# fire up the ngin
CMD ["nginx", "-g", "daemon off;"]
