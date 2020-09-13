FROM amazonlinux:2

ARG VERSION=3.8.5

SHELL ["/bin/bash", "-c"]
RUN yum update -y
RUN yum install -y gcc bzip2 bzip2-devel openssl openssl-devel readline readline-devel git wget gcc-c++ unixODBC-devel tar.x86_64 sqlite-devel

RUN echo 'export PYENV_ROOT="/usr/local/pyenv"' | tee -a /root/.bashrc
RUN echo 'export PATH="${PYENV_ROOT}/shims:${PYENV_ROOT}/bin:${PATH}"' | tee -a /root/.bashrc
RUN echo 'eval "$(pyenv init -)"' | tee -a /root/.bashrc

RUN git clone https://github.com/pyenv/pyenv.git /usr/local/pyenv
RUN source /root/.bashrc && pyenv install -v $VERSION && pyenv global $VERSION && pip install flake8
