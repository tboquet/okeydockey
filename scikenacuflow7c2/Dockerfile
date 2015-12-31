FROM tboquet/kenacuflow7c2

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install ggplot && conda install -y cython \
    pandas scikit-learn matplotlib \
    seaborn h5py yt sympy patsy \
    statsmodels

CMD ["/bin/bash"]
