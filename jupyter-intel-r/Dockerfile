FROM marcioaug/anaconda-intel

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

RUN conda update -y conda \
	&& conda install -y -c r r-essentials

ENTRYPOINT ["jupyter"]
CMD ["notebook", "--no-browser", "--notebook-dir=/opt/notebooks", "--ip=0.0.0.0", "--allow-root"]
