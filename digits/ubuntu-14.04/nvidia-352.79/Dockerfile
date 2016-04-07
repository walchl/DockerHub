FROM walchl/nvidia_digits-ubuntu_14.04:no_driver
MAINTAINER "Walter Chen-Hua Lu"

RUN cd /tmp &&\
    wget -q http://us.download.nvidia.com/XFree86/Linux-x86_64/352.79/NVIDIA-Linux-x86_64-352.79.run &&\
    sh NVIDIA-Linux-x86_64-*run -s -N --no-kernel-module &&\
    rm -rf *

