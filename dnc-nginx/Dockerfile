# Mostly got this from:
# https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/linux-nginx?tabs=aspnetcore2x
# https://serversforhackers.com/c/dckr-nginx-image

FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y nano
RUN apt-get install -y nginx
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Configure virtual host
ADD dnc-app.conf /etc/nginx/conf.d/dnc-app.conf

EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
