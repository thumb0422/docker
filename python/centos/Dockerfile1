#docker
docker pull centos
docker run --name=centos_uwsgi -p 8081:8081 -v /User/Liuchunhua/Document/share:/usr/local/work -td centos:latest /bin/bash
docker start centos_uwsgi
docker exec -it centos_uwsgi /bin/bash

#centos yum -y update
yum -y update

#gcc 
yum install gcc
yum install gcc-c++

#install  python3.7.0
yum install yum-utils
yum-builddep python
curl -O https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz
tar xf Python-3.7.0.tgz
cd Python-3.7.0
./configure
make
make install

#python3.7   enviroment
vi /etc/profile.d/python.sh
alias python='/usr/local/bin/python3.7'
source /etc/profile.d/python.sh
#pip 
curl -O https://bootstrap.pypa.io/get-pip.py
/usr/local/bin/python3.7 get-pip.py
#或
yum -y install python-pip
yum -y install epel-release

#uwsgi
pip install uwsgi

#nginx
yum install epel-release
yum install nginx

