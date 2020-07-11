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

# let's get python
# RUN yum -y install wget
# RUN wget https://www.python.org/ftp/python/3.8.3/Python-3.8.3.tgz
# RUN tar xvf Python-3.8.3.tgz



# make it from source
# RUN tar xvf Python-3.8.3.tgz
# WORKDIR Python-3.8.3
# RUN ./configure --enable-optimizations
# RUN make altinstall


RUN git clone https://github.com/pyenv/pyenv.git ~/.pyenv
ENV HOME  /root
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/shims:$PYENV_ROOT/bin:$PATH
RUN pyenv install 3.8.3
RUN pyenv global 3.8.3
RUN python --version
