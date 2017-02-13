FROM ubuntu:14.04

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update --fix-missing && apt-get install -y wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1 \
    git mercurial subversion

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh && \
    wget --no-check-certificate --quiet https://repo.continuum.io/miniconda/Miniconda3-4.0.5-Linux-x86_64.sh -O ~/miniconda.sh && \
    /bin/bash ~/miniconda.sh -b -p /opt/conda && \
    rm ~/miniconda.sh

ENV PATH /opt/conda/bin:$PATH

RUN pip install celery sqlalchemy flower && \
    conda install -y pandas h5py numpy scikit-learn && \
    pip install keras && \
    export C_FORCE_ROOT="true"

WORKDIR "/sched"

CMD ["celery", "-A", "alp.appcom", "flower", "--port=5555", "--broker_api=http://guest:guest@rabbitmq:15672/api/"]
