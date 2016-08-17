FROM tboquet/the7hc5workeralp

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

CMD ["celery", "worker", "-A", "alp.backend.keras_backend", "-Q", "sklearn", "-l", "INFO", "--maxtasksperchild=1", "--autoscale=6,1"]
