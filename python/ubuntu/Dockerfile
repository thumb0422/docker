FROM ubuntu:18.10

MAINTAINER lch0422 <lch0422@163.com>

RUN apt-get update && \
    apt-get upgrade -y && \ 	
    apt-get install -y \
    vim \
	git \
	python3 \
	python3-dev \
	python3-setuptools \
	python3-pip \
	supervisor \
	sqlite3 && \
	pip3 install -U pip setuptools && \
    rm -rf /var/lib/apt/lists/* 
RUN echo alias python='/usr/bin/python3.6' >> ~/.bashrc  && /bin/bash -c "source ~/.bashrc"

EXPOSE 80
CMD ["/bin/bash"]
