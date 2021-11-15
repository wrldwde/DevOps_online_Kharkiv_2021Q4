#----------------------------------------------------------------------------------
# Dockefile to build Docker Image of Apache WebServer running on latest AmazonLinux 
#
#----------------------------------------------------------------------------------

FROM amazonlinux:latest

RUN yum -y update
RUN yum -y install httpd

RUN echo '<h1>Hello, Wrldwde from Docker!</h1>' > /var/www/html/index.html
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

EXPOSE 80
