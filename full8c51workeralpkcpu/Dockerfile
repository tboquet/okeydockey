FROM tboquet/full8c51workeralpcpu

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

CMD ["celery", "worker", "-A", "alp.backend.keras_backend", "-Q", "keras", "-l", "INFO", "--maxtasksperchild=1", "--autoscale=6,1"]
