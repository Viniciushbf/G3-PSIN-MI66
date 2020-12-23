FROM centos:7

ENV vol='/var/www/html'
ENV gitG='https://github.com/Pio69/Intranet.git'
LABEL version="1.0" description="Centos/apache"

RUN yum update -y && yum install git -y  && yum install httpd -y

EXPOSE 80

VOLUME $vol:$vol
 
RUN git clone $gitG && cp -r  Intranet/* $vol

RUN cd /var/www/ && ls -l

CMD ["/usr/sbin/httpd","-D","FOREGROUND"]

