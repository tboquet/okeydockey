
FROM ubuntu:14.04

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update --fix-missing && apt-get install -y wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1 \
    git mercurial subversion

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh && \
    wget --quiet https://repo.continuum.io/miniconda/Miniconda-3.16.0-Linux-x86_64.sh && \
    /bin/bash /Miniconda-3.16.0-Linux-x86_64.sh -b -p /opt/conda && \
    rm Miniconda-3.16.0-Linux-x86_64.sh && \
    /opt/conda/bin/conda install --yes conda==3.18.3

ENV PATH /opt/conda/bin:$PATH

RUN conda install bokeh numpy scipy pandas && \
    pip install git+https://github.com/AgnezIO/agnez.git

WORKDIR "/visuserv"

CMD ["bokeh", "serve", "--address", "0.0.0.0", "--host", "192.168.128.129:5006" "--develop"]
# bokeh serve --address 0.0.0.0 --host 192.168.128.129:5006 --develop
