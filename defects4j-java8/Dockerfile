FROM alpine

LABEL mainteiner="Marcio Augusto Guimarães <marcioaugustosg@gmail.com"

RUN apk add --update --no-cache \
        git \
        subversion \
        openjdk8-jre \
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
        && cd /opt && git clone -b java-8-support https://github.com/rjust/defects4j \
        && cd defects4j && git branch && ./init.sh \
        && echo 'export PATH=/opt/defects4j/framework/bin:$PATH' > /etc/profile.d/defects4j.sh \
        && echo 'export PATH=/opt/defects4j/major/bin:$PATH' > /etc/profile.d/major.sh \
        && apk del .build-deps

ENV PATH /opt/defects4j/framework/bin:/opt/defects4j/major/bin:$PATH
ENV JAVA_TOOL_OPTIONS -Dmajor.export.context=true
ENV JAVA_OPTS -Xms256m -Xmx1024m -XX:PermSize=512m -XX:MaxPermSize=1024m
