ARG PYTORCH="1.2"
ARG CUDA="10.0"
ARG CUDNN="7"

FROM pytorch/pytorch:${PYTORCH}-cuda${CUDA}-cudnn${CUDNN}-runtime

RUN apt-get update && apt-get install -y tree vim htop libglib2.0-0 libsm6 libxrender-dev libxext6 \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

# latest visdom has fonts missing, see here: https://github.com/fossasia/visdom/issues/537
RUN pip install torch==1.4.0+cu100 torchvision==0.5.0+cu100 -f https://download.pytorch.org/whl/torch_stable.html
RUN pip install dominate==2.4.0 visdom==0.1.8.6
