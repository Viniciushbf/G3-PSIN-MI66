FROM centos:7
LABEL version="1.0" description="Centos/apache"
RUN yum update -y && yum install git -y  && yum install httpd -y
EXPOSE 80 
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

RUN git clone https://github.com/Pio69/Intranet.git && cp -r  Intranet/* /var/www/html

RUN cd /var/www/ && ls -l
