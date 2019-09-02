FROM centos:latest

ENV TZ "Asia/Shanghai"

RUN yum -y update
RUN yum -y groupinstall "Development Tools"
RUN yum -y install \ 
           kernel-devel \
           kernel-headers \
           gcc-c++ \
           patch \
           #libyaml-devel \
           libffi-devel \
           autoconf \
           automake \
           make \
           libtool \
           bison \
           #tk-devel \
           zip \
           wget \
           tar \
           gcc \
           zlib \
           zlib-devel \
          # bzip2 \
           bzip2-devel \
           #readline \
           #readline-devel \
          # sqlite \
           sqlite-devel \
           openssl \
           openssl-devel \
           git \
           gdbm-devel \
           python-devel \
           net-tools \
           vim

WORKDIR /root
RUN wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz
RUN tar xzvf Python-3.7.4.tgz

WORKDIR ./Python-3.7.4
#RUN ./configure --with-threads
RUN ./configure
RUN make install

RUN rm -rf /usr/src/python 
RUN cd /usr/local/bin \
    && ln -s python3.7 python \
    && yum clean all

RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python get-pip.py

#RUN pip install readline

WORKDIR /root
RUN rm -f Python-3.7.4.tgz \
    && rm -f anaconda-ks.cfg \
    && rm -rf Python-3.7.4

#Nginx
RUN rpm -ivh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
RUN yum -y install nginx

EXPOSE 8081
CMD ["/bin/bash"]
