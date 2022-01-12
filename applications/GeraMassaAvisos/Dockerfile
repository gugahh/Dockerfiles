FROM gugahh/ubuntu-oracle-nodejs:latest

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Aplicativo: gera massa de avisos para distribuicao e cadastra distribuidores"

ARG db_conn
ARG db_user
ARG db_passw

RUN	git clone https://github.com/gugahh/NodeJs.git \
	&& cd NodeJs/ExecutaDbOracle/ \
	&& npm install \
	&& echo $db_conn \
	&& echo $db_user \
	&& echo $db_passw \
	&& echo '#!/bin/sh' > run.sh \
	&& echo node GeraMassaTesteDistribuicao.js $db_conn $db_user $db_passw >> run.sh \
	&& echo node CadastraDistribuidores.js $db_conn $db_user $db_passw >> run.sh \
	&& cat run.sh \
	&& chmod +x run.sh  
		
WORKDIR NodeJs/ExecutaDbOracle

CMD /home/jenkins/NodeJs/ExecutaDbOracle/run.sh
