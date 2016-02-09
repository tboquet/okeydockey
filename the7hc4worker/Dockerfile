FROM tboquet/scikenacuthe7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN export C_FORCE_ROOT="true"

CMD ["celery", "worker", "-A", "scheduler.train", "-l", "INFO", "--maxtasksperchild=1", "--autoscale=6,1"]
