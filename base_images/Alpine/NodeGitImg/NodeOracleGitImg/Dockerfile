# syntax=docker/dockerfile:1
#Imagem baseada em Alpine Linux, com NodeJs, GIT e bash

#Download base image
#FROM alpine:3.3
FROM node:12-alpine

#USER docker

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Imagem baseada em Alpine Linux, com Oracle Instaclient, NodeJs, GIT e bash"

#RUN 	apk update
#RUN	apk upgrade
	
RUN	apk add bash	&& \
	apk add curl 	&& \
	apk add wget 	&& \
	apk add nano 	&& \
	apk add git 
	
# Install Instantclient Basic Light Oracle and Dependencies
ENV LD_LIBRARY_PATH=/lib

RUN wget https://download.oracle.com/otn_software/linux/instantclient/193000/instantclient-basic-linux.x64-19.3.0.0.0dbru.zip && \
    unzip instantclient-basic-linux.x64-19.3.0.0.0dbru.zip && \
    cp -r instantclient_19_3/* /lib && \
    rm -rf instantclient-basic-linux.x64-19.3.0.0.0dbru.zip && \
    apk add libaio && \
    apk add libaio libnsl libc6-compat && \
    cd /lib && \
    ln -s /lib64/* /lib && \
    ln -s libnsl.so.2 /usr/lib/libnsl.so.1 && \
    ln -s libc.so /usr/lib/libresolv.so.2

#ADD script.sh /root/script.sh

#RUN /root/script.sh
	
#Preparativos para o usuario do Jenkins, com permissoes de escrita em pasta
RUN 	mkdir /home/jenkins && \
	adduser -h /home/jenkins -s /bin/bash -D jenkins jenkins && \
	chown jenkins /home/jenkins
        
# groupadd -g jenkins jenkins && \
# addgroup -S jenkins && adduser -S jenkins -G jenkins && \
#
#	echo "$USER ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/$USER && \
#        chmod 0440 /etc/sudo\	ers.d/$USER

USER jenkins

#
# Expose port 80
# EXPOSE 80

CMD 	echo ' Imagem Alpine Linux 3.15 com Oracle Instaclient, NodeJs, Git e Bash disponiveis'
