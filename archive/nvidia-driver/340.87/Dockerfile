FROM ubuntu:14.04
MAINTAINER "Walter Chen-Hua Lu"
ONBUILD \
RUN apt-get update &&\
    apt-get -y install wget &&\
    apt-get clean
ONBUILD \
RUN cd /tmp &&\
    wget -q http://us.download.nvidia.com/XFree86/Linux-x86_64/340.87/NVIDIA-Linux-x86_64-340.87.run &&\
    sh NVIDIA-Linux-x86_64-340.87.run -s -N --no-kernel-module &&\
    rm -rf *
