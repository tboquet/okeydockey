FROM tboquet/scikenacuthe7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

ENV C_FORCE_ROOT="true"

RUN pip install dill

RUN pip install --upgrade git+git://github.com/tboquet/python-alp.git

CMD ["celery", "worker", "-A", "alp.backend.keras_backend", "-l", "INFO", "--maxtasksperchild=1", "--autoscale=6,1"]
