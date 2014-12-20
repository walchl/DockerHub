FROM centos
MAINTAINER "Walter Chen-Hua Lu"
RUN yum -y install vsftpd
RUN sed -i 's/^anonymous_enable=/anonymous_enable=NO\n#/g' /etc/vsftpd/vsftpd.conf &&\
    sed -i 's/^#chroot_local_user/chroot_local_user/g' /etc/vsftpd/vsftpd.conf &&\
    sed -i 's/^listen=/listen=YES\n#/g' /etc/vsftpd/vsftpd.conf &&\
    sed -i 's/^listen_ipv6=/listen_ipv6=NO\n#/g' /etc/vsftpd/vsftpd.conf &&\
    echo 'pasv_enable=NO' >> /etc/vsftpd/vsftpd.conf &&\
    echo 'background=NO' >> /etc/vsftpd/vsftpd.conf
RUN useradd -d /vsftp ieet &&\
    echo ieet:ieet | chpasswd
CMD ["vsftpd"]
