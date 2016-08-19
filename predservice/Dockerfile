FROM tboquet/the7hc5workeralp:py3

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN conda install Flask -y

RUN rm /root/.theanorc && \
    echo "[global]\ndevice=cpu\nfloatX=float32" > /root/.theanorc

RUN cd /root && git clone https://github.com/tboquet/predFactory.git

WORKDIR /root/predFactory

CMD ["python", "app.py"]
