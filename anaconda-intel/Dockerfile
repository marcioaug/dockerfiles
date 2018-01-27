FROM marcioaug/anaconda:debian

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN conda update -y conda \
        && conda config --add channels intel \
        && conda install -y pydotplus intelpython3_core
