FROM tboquet/kenacufull7hc5

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install ggplot celery sqlalchemy flower && \
    conda install -y cython \
    pandas scikit-learn matplotlib \
    seaborn h5py yt sympy patsy \
    statsmodels pymongo

CMD ["/bin/bash"]
