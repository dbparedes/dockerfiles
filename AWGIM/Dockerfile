FROM tensorflow/tensorflow:1.12.0-gpu-py3

RUN apt-get update && apt-get install -y tree vim htop \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN pip install tensorflow-probability
