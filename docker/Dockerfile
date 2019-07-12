FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu18.04

RUN mkdir /code
WORKDIR /code

RUN apt-get update -qqy && \
    apt-get install -qqy \
    ca-certificates \
    git curl wget \
    software-properties-common \
    python3 python3-pip libsm6 libxext6 libxrender-dev \
    --no-install-recommends && \
    apt-get -qqy clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip3 install opencv-python
RUN pip3 install https://download.pytorch.org/whl/cu100/torch-1.1.0-cp36-cp36m-linux_x86_64.whl
RUN pip3 install https://download.pytorch.org/whl/cu100/torchvision-0.3.0-cp36-cp36m-linux_x86_64.whl

RUN git clone https://github.com/bmaltais/ESRGAN.git esrgan --recursive
WORKDIR /code/esrgan
