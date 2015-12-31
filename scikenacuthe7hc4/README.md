[![Docker Stars](https://img.shields.io/docker/stars/_/ubuntu.svg)](https://hub.docker.com/r/tboquet/scikenacuthe7hc4/)[![Docker Pulls](https://img.shields.io/docker/pulls/mashape/kong.svg)](https://hub.docker.com/r/tboquet/scikenacuthe7hc4/)[![ImageLayers Size](https://img.shields.io/imagelayers/image-size/_/ubuntu/latest.svg)][![Docker Pulls](https://img.shields.io/docker/pulls/mashape/kong.svg)](https://hub.docker.com/r/tboquet/scikenacuthe7hc4/)[![ImageLayers Layers](https://img.shields.io/imagelayers/layers/_/ubuntu/latest.svg)](https://hub.docker.com/r/tboquet/scikenacuthe7hc4/)
**CUDA 7.5 + cuDNN v4 + Miniconda + Theano + Keras + scikit-learn + scipy stuffs**
==================================================================================
All images created have to be used with the cuda-nvidia script provided [here](https://github.com/NVIDIA/nvidia-docker)


**Example:**
============
If you want to use your GPU 0 (as listed by nvidia-smi), be able to serve an ipython notebook via the port 8888 and mount a volume where some notebooks are located you could use:
```
GPU=0 ./nvidia-docker run -it -p 8888:8888 -v ~/notebooks:/notebooks tboquet/scikenacuthe7hc4
```
