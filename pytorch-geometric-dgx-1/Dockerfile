ARG PYTORCH="1.6.0"
ARG CUDA="10.1"
ARG CUDNN="7"

FROM pytorch/pytorch:${PYTORCH}-cuda${CUDA}-cudnn${CUDNN}-runtime

RUN apt-get update && apt-get install -y tree vim htop libglib2.0-0 libsm6 libxrender-dev libxext6 \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN pip install tensorboardX packaging scikit-image scikit-learn
RUN pip install graphviz opencv-python-headless tensorboard jupyterlab Pillow

ARG CUDA="cu101"
RUN pip install torch-scatter -f https://pytorch-geometric.com/whl/torch-${PYTORCH}+${CUDA}.html
RUN pip install torch-sparse -f https://pytorch-geometric.com/whl/torch-${PYTORCH}+${CUDA}.html
RUN pip install torch-cluster -f https://pytorch-geometric.com/whl/torch-${PYTORCH}+${CUDA}.html
RUN pip install torch-spline-conv -f https://pytorch-geometric.com/whl/torch-${PYTORCH}+${CUDA}.html
RUN pip install torch-geometric
