FROM walchl/nvidia-driver:346.82
MAINTAINER "Walter Chen-Hua Lu"
RUN apt-get -y install wget build-essential freeglut3-dev libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev &&\
    apt-get clean
RUN cd /tmp &&\
    wget -q http://developer.download.nvidia.com/compute/cuda/7_0/Prod/local_installers/cuda_7.0.28_linux.run &&\
    sh cuda_7.0.28_linux.run -silent -toolkit &&\
    rm -rf *
RUN cd /usr/local/cuda/samples/1_Utilities/deviceQuery &&\
    make &&\
    cp -r /usr/local/cuda/samples/bin/x86_64/linux/release/* /usr/local/cuda/bin/.
RUN ln -s /usr/local/cuda/bin/* /usr/local/bin/. &&\
    ln -s /usr/local/cuda/lib64/* /usr/local/lib/.
