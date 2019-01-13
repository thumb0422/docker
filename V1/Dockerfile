# Pull base image
FROM centos:latest

# Maintener
MAINTAINER lch0422 <lch0422@163.com>

#设置时区
ENV TZ "Asia/Shanghai"

# Update CentOS 7
RUN yum update -y

# Install packages
#RUN yum install -y curl git

# Install EPEL Repository
RUN yum install -y epel-release

#gcc 
RUN yum install -y gcc gcc-c++

#install  python3.6
RUN yum install -y yum-utils \
    && yum -y install https://centos7.iuscommunity.org/ius-release.rpm \
    && yum -y install python36u \
    && python3.6 -V  \
    && yum install -y python36u-pip python-devel

#python3.6 enviroment
RUN  echo alias python='/usr/bin/python3.6' >/etc/profile.d/python.sh \
     && source /etc/profile.d/python.sh

#python pip
RUN pip3.6 install --upgrade pip && pip3.6 -V

#uwsgi
RUN pip3.6 install uwsgi

#nginx
RUN yum install -y nginx

# Clean CentOS 7
RUN yum clean all 

EXPOSE 8080
# Default command
CMD ["/bin/bash"]
