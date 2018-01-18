FROM marcioaug/anaconda

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN conda update -y conda \
        && conda config --add channels intel \
        && conda create -y -n idp intelpython3_core python=3
