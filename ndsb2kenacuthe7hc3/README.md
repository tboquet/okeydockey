[![Docker Stars](https://img.shields.io/docker/stars/tboquet/ndsb2kenacuthe7hc3.svg)](https://hub.docker.com/r/tboquet/ndsb2kenacuthe7hc3/)[![Docker Pulls](https://img.shields.io/docker/pulls/tboquet/ndsb2kenacuthe7hc3.svg)](https://hub.docker.com/r/tboquet/ndsb2kenacuthe7hc3/)[![ImageLayers Size](https://img.shields.io/imagelayers/image-size/tboquet/ndsb2kenacuthe7hc3/latest.svg)](https://imagelayers.io/?images=tboquet%2Fndsb2kenacuthe7hc3:latest)[![ImageLayers Layers](https://img.shields.io/imagelayers/layers/tboquet/ndsb2kenacuthe7hc3/latest.svg)](https://imagelayers.io/?images=tboquet%2Fndsb2kenacuthe7hc3:latest)
**CUDA 7.5 + cuDNN v4 + Miniconda + Theano + Keras + scikit-learn + scipy stuffs + visu tools**
===============================================================================================


**Example:**
============
If you want to use your GPU 0 (as listed by nvidia-smi), be able to serve an ipython notebook via the port 8888 and mount a volume where some notebooks are located you could use:
```
GPU=0 ./nvidia-docker run -it -p 8888:8888 -v ~/notebooks:/notebooks tboquet/ndsb2kenacuthe7hc3
```
