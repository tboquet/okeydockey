FROM tboquet/scikenacuthe7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN conda install Flask -y

RUN rm /root/.theanorc && \
    echo "[global]\ndevice=cpu\nfloatX=float32" > /root/.theanorc

WORKDIR /sched

CMD ["python", "app.py"]
