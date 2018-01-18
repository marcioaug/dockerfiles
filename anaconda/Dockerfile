FROM marcioaug/ubuntu

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

ENV ANACONDA_VERSION=5.0.1
RUN buildDeps='\
                    curl \
                    ca-certificates \
                    bzip2 \
              '\
        && apt-get update \
        && apt-get install -y $buildDeps --no-install-recommends \
        && rm -rf /var/lib/apt/list/* \
        && curl -o ~/anaconda3.sh https://repo.continuum.io/archive/Anaconda3-${ANACONDA_VERSION}-Linux-x86_64.sh \
        && /bin/bash ~/anaconda3.sh -b -p /opt/anaconda3 \
        && echo 'export PATH=/opt/anaconda3/bin:$PATH' > /etc/profile.d/conda.sh \
        && rm ~/anaconda3.sh \
        && apt-get purge -y --auto-remove $buildDeps

ENV PATH /opt/anaconda3/bin:$PATH