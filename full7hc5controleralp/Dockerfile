FROM tboquet/scikenacufull7hc5

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install dill

RUN conda install Pillow -y && \
    pip install git+git://github.com/mila-udem/fuel.git

# RUN pip install --upgrade git+git://github.com/tboquet/python-alp.git
RUN cd /root && git clone https://github.com/tboquet/python-alp.git && cd python-alp && \
  # Install
  python setup.py install

CMD ["ipython", "notebook"]
