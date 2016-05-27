FROM tboquet/kenacuthe7hc5

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install brewer2mpl celery sqlalchemy flower && \
    conda install -y cython \
    pandas scikit-learn matplotlib \
    seaborn h5py yt sympy patsy \
    statsmodels pymongo && \
    pip install ggplot

CMD ["/bin/bash"]
