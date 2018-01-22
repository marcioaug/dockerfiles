FROM marcioaug/anaconda

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN apt-get -y install graphviz \
        && conda update -y conda \
        && conda config --add channels intel \
        && conda create -y -n idp intelpython3_full python=3 \
        && conda install -y pydotplus -n idp
