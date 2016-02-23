FROM tboquet/scikenacuflow7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

ENV C_FORCE_ROOT="true"

WORKDIR /sched

CMD ["celery", "worker", "-A", "scheduler.train", "-l", "INFO", "--maxtasksperchild=1", "--concurrency=1"]
