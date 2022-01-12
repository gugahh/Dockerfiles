# syntax=docker/dockerfile:1
#Imagem baseada em Alpine Linux, com NodeJs, GIT e bash

#Download base image
#FROM alpine:3.3
FROM node:12-alpine

#USER docker

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Imagem baseada em Alpine Linux, com NodeJs, GIT e bash"

#RUN 	apk update
#RUN	apk upgrade
	
RUN	apk add bash	&& \
	apk add sudo 	&& \
	apk add curl 	&& \
	apk add wget 	&& \
	apk add nano 	&& \
	apk add git 
	
#Preparativos para o usuario do Jenkins, com permissoes de escrita em pasta
RUN 	mkdir /home/jenkins && \
	adduser -h /home/jenkins -s /bin/bash -D jenkins jenkins && \
	chown jenkins /home/jenkins
        
# groupadd -g jenkins jenkins && \
# addgroup -S jenkins && adduser -S jenkins -G jenkins && \
#
#	echo "$USER ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/$USER && \
#        chmod 0440 /etc/sudoers.d/$USER

USER jenkins

#
# Expose port 80
# EXPOSE 80

CMD 	echo ' Imagem Alpine Linux 3.15 com Git, Node e Bash disponivel'
