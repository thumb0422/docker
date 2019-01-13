# Pull base image
FROM centos:latest

# Maintener
MAINTAINER lch0422 <lch0422@163.com>

#设置时区
ENV TZ "Asia/Shanghai"

# Update CentOS 7 && library
RUN yum update -y && yum -y install wget \
									gcc \
									gcc-c++ \
									automake \
									autoconf \
									libtool \
									make \
									openssl-devel \
									bzip2-devel \
									expat-devel \
									gdbm-devel \
									readline-devel \
									sqlite-devel \
									libxml*

#Download python
RUN cd /home/ 	&& wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz \
				&& tar -zxvf Python-3.6.5.tgz && cd Python-3.6.5 \
			   	&& ./configure --prefix=/usr/local/python3 \
			   	&& make -j2 && make install -j2

#python3.6.5 enviroment
RUN	echo alias python='/usr/local/python3/bin/python3.6.5' >> /etc/profile.d/python.sh \
	&& echo alias pip='/usr/local/python3/bin/pip3' >> /etc/profile.d/python.sh \
    && source /etc/profile.d/python.sh

RUN pip -V 
#python pip
RUN pip install --upgrade pip && pip -V

#uwsgi
RUN pip install uwsgi && \
	echo alias uwsgi='/usr/local/python3/bin/uwsgi' >> /etc/profile.d/python.sh \
	&& source /etc/profile.d/python.sh

#nginx
#RUN yum -y install nginx

# Clean CentOS 7
RUN yum clean all 

EXPOSE 8080
# Default command
CMD ["/bin/bash"]
