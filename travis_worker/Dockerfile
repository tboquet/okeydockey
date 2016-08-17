FROM ubuntu:14.04

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update --fix-missing && apt-get install -y curl wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1 \
    git mercurial subversion

RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh && \
    wget --no-check-certificate --quiet https://repo.continuum.io/miniconda/Miniconda2-4.0.5-Linux-x86_64.sh && \
    /bin/bash /Miniconda2-4.0.5-Linux-x86_64.sh -b -p /opt/conda && \
    rm Miniconda2-4.0.5-Linux-x86_64.sh

RUN apt-get install -y grep sed dpkg && \
    TINI_VERSION=`curl https://github.com/krallin/tini/releases/latest | grep -o "/v.*\"" | sed 's:^..\(.*\).$:\1:'` && \
    curl -L "https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini_${TINI_VERSION}.deb" > tini.deb && \
    dpkg -i tini.deb && \
    rm tini.deb && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV PATH /opt/conda/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8


RUN apt-get update --fix-missing && apt-get install -y libopenblas-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN conda install nose numpy scipy six -y

RUN pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git

RUN rm -f /root/.theanorc && \
    echo "[global]\ndevice=cpu\nfloatX=float32" > /root/.theanorc

ENV C_FORCE_ROOT="true"

RUN pip install dill

RUN pip install --upgrade git+git://github.com/tboquet/python-alp.git

RUN apt-get update && apt-get install -y \
    libhdf5-dev

# Install dependencies
RUN conda install -y ipython jupyter pyyaml pytables

RUN apt-get install -y graphviz graphviz-dev --no-install-recommends
RUN pip install pydot-ng

# Clone Keras repo and move into it
RUN cd /root && git clone https://github.com/fchollet/keras.git && cd keras && \
  # Install
  python setup.py install

RUN mkdir -p -m 700 /root/.jupyter/ && \
    echo "c.NotebookApp.ip = '*'" >> /root/.jupyter/jupyter_notebook_config.py

RUN pip install brewer2mpl celery sqlalchemy flower && \
    conda install -y cython statsmodels Pillow  \
    pandas scikit-learn \
    h5py yt sympy patsy \
    pymongo && \
    pip install ggplot && \
    pip install git+git://github.com/mila-udem/fuel.git

ENTRYPOINT [ "/usr/bin/tini", "--" ]

CMD ["celery", "worker", "-A", "alp.backend.keras_backend", "-l", "INFO", "--maxtasksperchild=1", "--autoscale=6,1"]

