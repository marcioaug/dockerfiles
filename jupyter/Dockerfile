FROM marcioaug/miniconda

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

RUN mkdir -p /opt/notebooks \
	&& conda update -y conda \
	&& conda install -y \
		jupyter \
		scikit-learn \
		tensorflow \
		matplotlib \
		seaborn \
 		pandas \
		theano \
		keras \
		statsmodels

ENTRYPOINT ["jupyter"]
CMD ["notebook", "--no-browser", "--notebook-dir=/opt/notebooks", "--ip=0.0.0.0", "--allow-root"]

