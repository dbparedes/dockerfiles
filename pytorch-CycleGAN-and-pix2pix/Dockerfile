FROM nvidia/cuda:10.0-base

RUN apt-get update && apt-get install -y wget unzip curl bzip2 git tree vim htop && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

RUN curl -LO http://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh
RUN bash Miniconda-latest-Linux-x86_64.sh -p /miniconda -b
RUN rm Miniconda-latest-Linux-x86_64.sh

ENV PATH=/miniconda/bin:${PATH}
RUN conda update -y conda

RUN conda install -y pytorch=1.4.0 torchvision cudatoolkit=10.0 -c pytorch
RUN conda install -y dominate=2.4.0 visdom=0.1.8.3 -c conda-forge
