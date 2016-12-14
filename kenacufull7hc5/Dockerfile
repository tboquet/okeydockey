FROM tboquet/anacufull7hc5

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

RUN mkdir .keras

RUN echo '{"epsilon": 1e-07, "floatx": "float32", "backend": "tensorflow"}' > /root/.keras/keras.json

RUN mkdir -p -m 700 /root/.jupyter/ && \
    echo "c.NotebookApp.ip = '*'" >> /root/.jupyter/jupyter_notebook_config.py
    echo "c.NotebookApp.password = 'sha1:3f84353ad3f5:d1b6eeb440acbc49330646714898ae27c8dd56c2'" >> /root/.jupyter/jupyter_notebook_config.py
VOLUME /notebooks
WORKDIR /notebooks

# IPython
EXPOSE 8888

# TensorBoard
EXPOSE 6006

CMD ["/bin/bash"]
