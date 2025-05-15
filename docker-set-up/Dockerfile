FROM nvidia/cuda:11.8.0-base-ubuntu20.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
    wget \
    && rm -rf /var/lib/apt/lists/*

RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda && \
    eval "$(/root/miniconda/bin/conda shell.bash hook)" && \
    conda init && \
    pip install pyyaml && \
    conda install -y pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia && \
    conda install -y matplotlib pandas scikit-learn

WORKDIR /evolveGCN
ENTRYPOINT /bin/bash

