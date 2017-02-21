FROM node:4

EXPOSE 4000

RUN cd /root && git clone https://github.com/keplr-io/hera.git \
    && cd hera

WORKDIR /root/hera

CMD ['bin', 'bash']
