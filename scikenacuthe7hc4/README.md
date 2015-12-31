**CUDA 7.5 + cuDNN v4 + Miniconda + Theano + Keras + scikit-learn + scipy stuffs**
==================================================================================
All images created have to be used with the cuda-nvidia script provided [here](https://github.com/NVIDIA/nvidia-docker)


**Example:**
============
If you want to use your GPU 0 (as listed by nvidia-smi), be able to serve an ipython notebook via the port 8888 and mount a volume where some notebooks are located you could use:
```
GPU=0 ./nvidia-docker run -it -p 8888:8888 -v ~/notebooks:/notebooks tboquet/scikenacuthe7hc4
```
