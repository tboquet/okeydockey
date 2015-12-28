FROM tboquet/anacuflow7c2

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update && apt-get install -y \
    libhdf5-dev

# Install dependencies
RUN conda install -y ipython jupyter h5py pyyaml

# Clone Keras repo and move into it
RUN cd /root && git clone https://github.com/fchollet/keras.git && cd keras && \
  # Install
  python setup.py install

RUN mkdir .keras

RUN echo '{"epsilon": 1e-07, "floatx": "float32", "backend": "tensorflow"}' > /root/.keras/keras.json
# IPython
EXPOSE 8888

WORKDIR "/root"

CMD ["/bin/bash"]
