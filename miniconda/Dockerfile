FROM debian:stable-slim

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

ENV MINICONDA_URL "https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh"

RUN buildDeps='\
		    curl \
		    ca-certificates \
		    bzip2 \
	      '\
	&& apt-get update \
	&& apt-get install -y $buildDeps --no-install-recommends \
	&& rm -rf /var/lib/apt/list/* \
	&& curl -o ~/miniconda3.sh ${MINICONDA_URL} \
	&& /bin/bash ~/miniconda3.sh -b -p /opt/conda \
	&& echo "export PATH=/opt/conda/bin:$PATH" > /etc/profile.d/conda.sh \
	&& rm ~/miniconda3.sh \
	&& apt-get purge -y --auto-remove $buildDeps

RUN apt-get install -y --no-install-recommends \
	libglib2.0-0 \
	libxext6 \
	libsm6 \ 
	libxrender1 \
	graphviz \
	&& rm -rf /var/lib/apt/list/*

ENV PATH /opt/conda/bin:$PATH

