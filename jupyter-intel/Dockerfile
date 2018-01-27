FROM marcioaug/jupyter

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

RUN conda update -y conda \
	&& conda config --add channels intel \
	&& conda install -y intelpython3_core

