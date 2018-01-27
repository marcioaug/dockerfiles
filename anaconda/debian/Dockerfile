FROM debian:stable-slim

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

ENV ANACONDA_VERSION 5.0.1
ENV ANACONDA_URL "https://repo.continuum.io/archive/Anaconda3-${ANACONDA_VERSION}-Linux-x86_64.sh"

RUN buildDeps='\
		    curl \
		    ca-certificates \
		    bzip2 \
	      '\
	&& apt-get update \
	&& apt-get install -y $buildDeps --no-install-recommends \
	&& rm -rf /var/lib/apt/list/* \
	&& curl -o ~/anaconda3.sh ${ANACONDA_URL} \
	&& /bin/bash ~/anaconda3.sh -b -p /opt/anaconda3 \
	&& echo "export PATH=/opt/anaconda3/bin:$PATH" > /etc/profile.d/conda.sh \
	&& rm ~/anaconda3.sh \
	&& apt-get purge -y --auto-remove $buildDeps

RUN apt-get install -y --no-install-recommends \
	libglib2.0-0 \
	libxext6 \
	libsm6 \ 
	libxrender1 \
	graphviz \
	&& rm -rf /var/lib/apt/list/*

ENV PATH /opt/anaconda3/bin:$PATH
