
FROM continuumio/miniconda:py27_latest

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install celery sqlalchemy flower

WORKDIR "/sched"

CMD ["/bin/bash"]
