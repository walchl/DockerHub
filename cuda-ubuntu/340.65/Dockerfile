FROM ubuntu:14.04
MAINTAINER "Walter Chen-Hua Lu"
RUN apt-get update &&\
    apt-get -y install wget build-essential freeglut3-dev libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev
RUN cd /tmp &&\
    wget -q http://developer.download.nvidia.com/compute/cuda/6_5/rel/installers/cuda_6.5.14_linux_64.run &&\
    sh cuda_6.5.14_linux_64.run -silent -toolkit -toolkitpath=/usr/local &&\
    rm -rf * &&\
    mv /usr/local/lib64/* /usr/local/lib/. &&\
    rm -rf /usr/local/lib64
RUN cd /usr/local/samples/1_Utilities/deviceQuery &&\
    make &&\
    cp -r /usr/local/samples/bin/x86_64/linux/release/* /usr/local/bin/.
RUN cd /tmp &&\
    wget -q http://http.download.nvidia.com/XFree86/Linux-x86_64/340.65/NVIDIA-Linux-x86_64-340.65.run &&\
    sh NVIDIA-Linux-x86_64-340.65.run -s -N --no-kernel-module &&\
    rm -rf *
