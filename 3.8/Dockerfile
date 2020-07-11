# latest Amazon Linux
FROM amazonlinux:latest
RUN yum -y update

# required by Circle
RUN yum -y install git tar gzip ca-certificates

# required by python
RUN yum -y groupinstall "Development Tools"
RUN yum -y install openssl-devel bzip2-devel libffi-devel

# check we have gcc
RUN gcc --version

# install pyenv
RUN git clone https://github.com/pyenv/pyenv.git ~/.pyenv
ENV HOME  /root
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH

# use pyenv to install latest version
RUN pyenv install 3.8.3

# set it as global
RUN pyenv global 3.8.3

# check python version
RUN python --version
