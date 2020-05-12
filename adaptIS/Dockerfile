ARG PYTORCH="1.2"
ARG CUDA="10.0"
ARG CUDNN="7"

FROM pytorch/pytorch:${PYTORCH}-cuda${CUDA}-cudnn${CUDNN}-devel

RUN apt-get update && apt-get install -y tree vim htop libglib2.0-0 libsm6 libxrender-dev libxext6 \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN conda install pytorch==1.3.0 torchvision==0.4.1 cudatoolkit=10.0 -c pytorch

RUN pip install graphviz opencv-python-headless albumentations tensorboard cython easydict bridson jupyterlab
