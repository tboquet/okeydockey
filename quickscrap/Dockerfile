FROM tboquet/scikenacufull7hc5:py3

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install --upgrade celery beautifulsoup4

RUN conda install -y Pillow lxml

ENV C_FORCE_ROOT='true'

WORKDIR /notebooks

CMD ["jupyter", "notebook"]
