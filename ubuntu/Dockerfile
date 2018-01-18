FROM ubuntu:artful

LABEL maintainer = "Marcio Augusto Guimarães <marcioaugustosg@gmail.com>"

RUN apt-get update && apt-get install -y \
        git \
        zsh \
        --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
        && chsh -s /bin/zsh

ENV SHELL /usr/bin/zsh


RUN buildDeps='  \
                 ca-certificates \
                 curl \
              ' \
        && set -x \
        && apt-get update && apt-get install -y $buildDeps --no-install-recommends \
        && rm -rf /var/lib/apt/list/* \
        && sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)" \
        && apt-get purge -y --auto-remove $buildDeps

COPY ./.zshrc /root/.zshrc

WORKDIR "/root"
ENTRYPOINT ["/bin/zsh"]
