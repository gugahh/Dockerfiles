FROM oraclelinux:8

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Imagem baseada em Oracle Linux, com Oracle Instaclient, NodeJs, GIT e bash"

#Instalacao Oracle -
#Instalacao NodeJs


RUN		dnf install git nodejs npm  --assumeyes \
	&& 	dnf install oracle-instantclient-release-el8 --assumeyes \
	&& 	dnf install oracle-instantclient-basic --assumeyes \
	&& 	useradd jenkins 
	
	
# && useradd -p jenkins \
# && usermod -aG sudo jenkins \
 
    
#	&& apt-get install nodejs npm sudo --assume-yes \
#    && dpkg -i /usr/local/etc/oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb \
#    && rm /usr/local/etc/oracle-instantclient-basiclite_21.4.0.0.0-2_amd64.deb \    
    
#Preparativos para o usuario do Jenkins, com permissoes de escrita em pasta
# RUN 	useradd -m jenkins
	
USER jenkins
#USER root

CMD 	echo ' Imagem OracleLinux com Oracle Instaclient, NodeJs, Git e Bash disponiveis'
