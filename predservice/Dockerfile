FROM tboquet/the7hc5workeralp:py3

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN conda install Flask -y

RUN rm /root/.theanorc && \
    echo "[global]\ndevice=cpu\nfloatX=float32" > /root/.theanorc

RUN cd /root && git clone https://github.com/tboquet/predFactory.git

RUN cd /root && git clone https://github.com/tboquet/python-alp.git && cd python-alp && \

WORKDIR /root/predFactory

CMD ["python", "app.py"]
