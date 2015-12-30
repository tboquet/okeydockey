FROM tboquet/kenacuthe7hc4

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN pip install ggplot
RUN conda install -y cython
RUN conda install -y pandas scikit-learn
RUN conda install -y matplotlib
RUN conda install -y seaborn
RUN conda install -y h5py
RUN conda install -y yt
RUN conda install -y sympy
RUN conda install -y patsy
RUN conda install -y statsmodels

CMD ["/bin/bash"]
