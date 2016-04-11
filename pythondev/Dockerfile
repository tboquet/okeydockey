
FROM themattrix/tox

MAINTAINER Thomas Boquet <thomas.boquet@hec.ca>

RUN apt-get install -y gfortran build-essential \
    make gcc build-essential git-core curl wget \
    vim-tiny nano

# RUN mkdir -p /root/src && \
#     cd /root/src/ && \
#     wget http://www.netlib.org/lapack/lapack.tgz && \
#     tar xzf lapack.tgz && \
#     cd lapack-*/ && \
#     cp INSTALL/make.inc.gfortran make.inc && \
#     sed -i 's/OPTS     = -O2/OPTS = -O2 -fPIC -m64/g' make.inc && \
#     sed -i 's/NOOPT    = -O0/NOOPT = -O0 -fPIC -m64/g' make.inc && \
#     make lapacklib && \
#     make clean && \
#     cp liblapack.a /usr/local/lib && \
#     echo "Created liblapack.a in /usr/local/lib" && \
#     rm -r -f /root/src && \

# RUN apt-get install libblas-dev liblapack-dev

RUN apt-get update --fix-missing && apt-get install -y libopenblas-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

CMD cp -rT /src/ /app/ && tox
