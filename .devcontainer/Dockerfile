FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-3.16
RUN apk update && apk add \
  git vim \
  bash bash-dev bash-doc bash-dbg bash-completion \
  make automake autoconf texinfo \
  shellcheck shellcheck-doc shfmt \
  py3-pygments

RUN ln -s /usr/bin/python3 /usr/bin/python

WORKDIR /bashdb
RUN git clone --branch bash-5.1 https://git.code.sf.net/p/bashdb/code /bashdb
RUN ./autogen.sh && \
  ./configure && \
  make && \
  make install

WORKDIR /vscode
RUN rm -rf /bashdb
