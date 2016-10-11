FROM tboquet/anacuda7hc5

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update --fix-missing && apt-get install -y libopenblas-dev \
        curl \
        libfreetype6-dev \
        libpng12-dev \
        libzmq3-dev \
        pkg-config && \
        apt-get clean && \
        rm -rf /var/lib/apt/lists/*

RUN conda install nose numpy scipy six -y

# Install TensorFlow GPU version.
ENV TENSORFLOW_VERSION 0.11.0rc0
RUN pip --no-cache-dir install \
    https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-${TENSORFLOW_VERSION}-cp27-none-linux_x86_64.whl

# TensorBoard
EXPOSE 6006
# IPython
EXPOSE 8888

WORKDIR "/root"
