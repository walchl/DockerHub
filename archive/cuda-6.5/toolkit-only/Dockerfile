FROM ubuntu:14.04
MAINTAINER "Walter Chen-Hua Lu"
ONBUILD \
RUN apt-get update &&\
    apt-get -y install wget build-essential freeglut3-dev libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev &&\
    apt-get clean
ONBUILD \
RUN cd /tmp &&\
    wget -q http://developer.download.nvidia.com/compute/cuda/6_5/rel/installers/cuda_6.5.14_linux_64.run &&\
    sh cuda_6.5.14_linux_64.run -silent -toolkit &&\
    rm -rf *
ONBUILD \
RUN cd /usr/local/cuda/samples/1_Utilities/deviceQuery &&\
    make &&\
    cp -r /usr/local/cuda/samples/bin/x86_64/linux/release/* /usr/local/cuda/bin/.
ONBUILD \
RUN ln -s /usr/local/cuda/bin/* /usr/local/bin/. &&\
    ln -s /usr/local/cuda/lib64/* /usr/local/lib/.
