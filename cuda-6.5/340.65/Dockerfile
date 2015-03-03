FROM walchl/cuda-6.5:toolkit-only
MAINTAINER "Walter Chen-Hua Lu"
RUN cd /tmp &&\
    wget -q http://http.download.nvidia.com/XFree86/Linux-x86_64/340.65/NVIDIA-Linux-x86_64-340.65.run &&\
    sh NVIDIA-Linux-x86_64-340.65.run -s -N --no-kernel-module &&\
    rm -rf *
