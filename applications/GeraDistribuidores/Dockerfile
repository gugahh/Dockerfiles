FROM gugahh/ubuntu-oracle-nodejs:latest

LABEL maintainer="gugahh.br@gmail.com"
LABEL version="0.1"
LABEL description="Aplicativo: gera massa de avisos para distribuicao e cadastra distribuidores"


RUN	cd /home/jenkins/ \
	&& git clone https://github.com/gugahh/NodeJs.git \
	&& cd /home/jenkins/NodeJs/ExecutaDbOracle/ \
	&& npm install

CMD 	cd /home/jenkins/NodeJs/ExecutaDbOracle/ \
	&& node GeraMassaTesteDistribuicao.js ${str_conexao} ${login_db} ${senha_db} \
	&& node CadastraDistribuidores.js ${str_conexao} ${login_db} ${senha_db}
