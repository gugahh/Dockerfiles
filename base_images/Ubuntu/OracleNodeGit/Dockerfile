FROM ubuntu:latest

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Imagem baseada em Ubuntu:latest, com Oracle Instaclient, NodeJs, GIT e bash"

ENV DEBIAN_FRONTEND noninteractive

# COPY  assets/oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb /usr/local/etc/oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb

ARG ftp_repo_user
ARG ftp_repo_passwd
ARG ftp_repo_home_addr

# Cria usuario para o jenkins (linha 19 - 20), com ids de grupo e usuario usados pelo Jenkins
# Instalacao NodeJs e outros apps (linhas 21 e 23)
# Instalacao Oracle Instaclient (linhas 22 e 24 a 26)
RUN	apt-get update \
	&& groupadd --gid 137 jenkins \
	&& useradd -u 127 --gid 137 -p jenkins -m jenkins -s /bin/bash -c "Bem-vindo, Jenkins user!" \
	&& apt-get install wget --assume-yes \
	&& wget ftp://$ftp_repo_user:$ftp_repo_passwd@$ftp_repo_home_addr/volume1/Install/OracleClient/Debian/oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb \
	&& apt-get install git libaio1 nodejs npm --assume-yes \
	&& dpkg -i oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb \
	&& echo /usr/lib/oracle/21/client64/lib/ > /etc/ld.so.conf.d/oracle.conf \
	&& ldconfig \
	&& rm oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb
    
# Cria senha pro usuario jenkins, para poder utilizar com SUDO (linha 19)
# && echo -e "8hLm7BS37w@_xfjg\n8hLm7BS37w@_xfjg" | passwd jenkins \
# && usermod -aG sudo jenkins \
# install curl wget nano

USER jenkins

WORKDIR /home/jenkins/

#CMD 	echo ' Imagem Ubuntu latest com Oracle Instaclient, NodeJs, Git e Bash disponiveis'
