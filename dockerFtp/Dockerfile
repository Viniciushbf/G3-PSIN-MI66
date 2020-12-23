# Dockerfile for vsftpd on CentOS
FROM centos:7
RUN yum -y update; yum -y install vsftpd net-tools vsftpd-sysvinit; yum clean all

COPY vusers.txt /etc/vsftpd/

RUN db_load -T -t hash -f /etc/vsftpd/vusers.txt /etc/vsftpd/vsftpd-virtual-user.db; rm -v /etc/vsftpd/vusers.txt; chmod 600 /etc/vsftpd/vsftpd-virtual-user.db

COPY vsftpd.conf /etc/vsftpd/
COPY vsftpd.virtual /etc/pam.d/

RUN mkdir -p /home/vsftpd/anon ;chmod -R 777 /home/vsftpd/anon; chown -R ftp:ftp /home/vsftpd/; chmod 775 /home/vsftpd

EXPOSE 20 21 30000 31000
CMD ["/usr/sbin/vsftpd","-obackground=NO"]
