# Mostly got this from: https://access.redhat.com/articles/1328953

FROM centos:latest
USER root

# Fix per https://bugzilla.redhat.com/show_bug.cgi?id=1192200 
RUN yum -y install deltarpm yum-utils --disablerepo=*-eus-* --disablerepo=*-htb-* \
    --disablerepo=*-ha-* --disablerepo=*-rt-* --disablerepo=*-lb-* --disablerepo=*-rs-* --disablerepo=*-sap-*

RUN yum-config-manager --disable *-eus-* *-htb-* *-ha-* *-rt-* *-lb-* *-rs-* *-sap-* > /dev/null

# Install dependencies
RUN yum update -y
RUN yum install nano

# Install Apache
RUN yum install httpd

# Make index.html
RUN echo "Apache is running!" > /var/www/html/index.html

# Configure apache
ADD dnc-app.conf /etc/httpd/conf.d/000-default.conf

EXPOSE 80

CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
