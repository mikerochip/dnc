# Mostly got this from:
# https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/linux-nginx?tabs=aspnetcore2x
# https://serversforhackers.com/c/dckr-nginx-image

FROM ubuntu:16.04

# software
RUN apt-get update
RUN apt-get install -y nano
RUN apt-get install -y nginx
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# configuration files
ADD ./etc/nginx/conf.d/dnc-app-1.conf /etc/nginx/conf.d/dnc-app-1.conf
ADD ./etc/nginx/mime.types /etc/nginx/mime.types
ADD ./etc/nginx/nginx.conf /etc/nginx/nginx.conf

# ports
EXPOSE 80

# run
CMD ["nginx", "-g", "daemon off;"]
