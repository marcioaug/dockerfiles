FROM alpine

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN apk add --update --no-cache \
        git \
        subversion \
        openjdk7-jre \
        perl \
        patch \
        bash \
        perl-dev \
        coreutils


RUN apk add --no-cache --virtual .build-deps \
                    unzip \
                    wget \
                    gcc \
                    g++ \
                    make \
                    curl \
        && curl -L http://xrl.us/cpanm > /bin/cpanm && chmod +x /bin/cpanm \
        && cpanm DBI \
        && mkdir /opt \
        && cd /opt && git clone https://github.com/marcioaug/defects4j \
        && cd defects4j && ./init.sh \
        && echo 'export PATH=/opt/defects4j/framework/bin:$PATH' > /etc/profile.d/defects4j.sh \
        && echo 'export PATH=/opt/defects4j/major/bin:$PATH' > /etc/profile.d/major.sh \
        && apk del .build-deps

ENV PATH /opt/defects4j/framework/bin:/opt/defects4j/major/bin:$PATH
ENV JAVA_TOOL_OPTIONS -Dmajor.export.context=true 
