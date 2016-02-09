FROM tboquet/anacuthe7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update && apt-get install -y \
    libhdf5-dev

# Install dependencies
RUN conda install -y ipython jupyter h5py pyyaml matplotlib pandas pytables

RUN apt-get install -y graphviz graphviz-dev --no-install-recommends
RUN pip install pydot

# Clone Keras repo and move into it
RUN cd /root && git clone https://github.com/fchollet/keras.git && cd keras && \
  # Install
  python setup.py install


RUN mkdir -p -m 700 /root/.jupyter/ && \
    echo "c.NotebookApp.ip = '*'" >> /root/.jupyter/jupyter_notebook_config.py

# IPython
EXPOSE 8888

CMD ["/bin/bash"]
