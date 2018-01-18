FROM marcioaug/intel-anaconda

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN apt-get update && apt-get install -y \
        subversion \
        openjdk-8-jre \
        --no-install-recommends \
        && rm -rf /var/lib/apt/lists/*

RUN buildDeps='\
                    unzip \
                    wget \
              '\
        && apt-get update \
        && apt-get install -y $buildDeps --no-install-recommends \
        && rm -rf /var/lib/apt/list/* \
        && cd /opt && git clone https://github.com/rjust/defects4j \
        && cd defects4j && ./init.sh \
        && echo 'export PATH=/opt/defects4j/framework/bin:$PATH' > /etc/profile.d/defects4j.sh \
        && echo 'export PATH=/opt/defects4j/major/bin:$PATH' > /etc/profile.d/major.sh \
        && apt-get purge -y --auto-remove $buildDeps

ENV PATH /opt/defects4j/framework/bin:/opt/defects4j/major/bin:$PATH