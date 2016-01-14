
FROM continuumio/miniconda:py27_latest

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install celery sqlalchemy flower && \
    export C_FORCE_ROOT="true"

ENV PATH /opt/conda/bin:$PATH

CMD ["/bin/bash"]
