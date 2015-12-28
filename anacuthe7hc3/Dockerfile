FROM tboquet/anacuda7hc3

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get update --fix-missing && apt-get install -y libopenblas-dev

RUN conda install nose numpy scipy six -y

RUN pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git

RUN echo "[global]\ndevice=gpu\nfloatX=float32\n[nvcc]\nfastmath=True" > /root/.theanorc

WORKDIR "/root"

CMD ["/bin/bash"]
