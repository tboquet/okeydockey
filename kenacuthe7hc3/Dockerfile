FROM tboquet/anacuthe7hc3

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update && apt-get install -y \
    libhdf5-dev

# Clone Keras repo and move into it
RUN cd /root && git clone https://github.com/fchollet/keras.git && cd keras && \
  # Install
  python setup.py install

RUN pip install -y ipython jupyter

# IPython
EXPOSE 8888

WORKDIR "/root"

CMD ["/bin/bash"]
