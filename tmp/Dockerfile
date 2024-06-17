#FROM pytorch/pytorch:1.9.0-cuda11.1-cudnn8-devel
FROM pytorch/pytorch:1.11.0-cuda11.3-cudnn8-devel

ENV DEBIAN_FRONTEND=noninteractive

# RUN conda update -n base -c defaults conda && \
#     conda install -y python=3.8 && \
#     conda update --all --yes

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys A4B469963BF863CC \
 && apt-get -y update \
 && apt-get -y install \
    libx264-dev \
    ffmpeg \
    libgl1-mesa-glx libglib2.0-0 libsm6 \
    wget curl cmake build-essential pkg-config \
    libxext6 libxrender-dev ffmpeg git

RUN apt-get -y update 
# && apt-get -y install \
#     cmake git
    
RUN apt-get clean && rm -rf /tmp/* /var/tmp/* \
 && python3 -m pip install --upgrade pip \
 && python3 -m pip install --upgrade setuptools


WORKDIR /workspace

RUN pip3 install --no-cache-dir -Iv \
    # numpy==1.20.3 opencv-python==4.3.0.38 onnx==1.12.0 \
    # # numpy opencv-python==4.5.5.64 onnx \
    # onnxruntime-gpu==1.7.0 mxnet-cu111 mxnet-mkl scikit-image \
    # # onnxruntime-gpu mxnet-cu116 mxnet-mkl scikit-image \
    # insightface==0.2.0 requests kornia==0.5.11 dill wandb \
    # # insightface requests kornia dill wandb \
    # # insightface requests kornia==0.5.11 dill wandb \
    # notebook ipython ipykernel psutil==5.9.2 \
    # ##from here it is for MAE environment
    # timm==0.4.12 matplotlib info-nce-pytorch \
    # retinaface_pytorch face-alignment
    numpy==1.23.5 pillow==9.4.0 opencv-python==4.8.0.76 opencv-contrib-python==4.8.0.76 \
    xformers==0.0.22.post7 accelerate==0.26.1 diffusers==0.14.0 transformers==4.27.3 \
    ftfy==6.1.3 clean-fid==0.1.35 torchmetrics==1.3.0.post0 mmcv mmengine==0.10.3 \
    mmpose==1.3.1 xtcocotools==1.14.3 munkres==1.1.4 jax==0.4.19 jaxlib==0.4.19 streamlit==1.34.0 \
    pyngrok==7.1.6
