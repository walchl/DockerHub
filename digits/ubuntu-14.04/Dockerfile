FROM ubuntu:14.04
MAINTAINER "Walter Chen-Hua Lu"

ONBUILD \
RUN apt-get update &&\
    apt-get -y install wget &&\
    apt-get clean 

ONBUILD \
RUN cd /tmp &&\
    CUDA_REPO_PKG=cuda-repo-ubuntu1404_7.5-18_amd64.deb &&\
    wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/$CUDA_REPO_PKG &&\
    dpkg -i $CUDA_REPO_PKG &&\
    rm -f $ML_REPO_PKG

ONBUILD \
RUN cd /tmp &&\
    ML_REPO_PKG=nvidia-machine-learning-repo_4.0-2_amd64.deb &&\
    wget http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1404/x86_64/$ML_REPO_PKG &&\
    dpkg -i $ML_REPO_PKG &&\
    rm -f $ML_REPO_PKG

ONBUILD \
RUN apt-get update &&\
    apt-get -y install digits &&\
    apt-get clean

ONBUILD \
RUN mkdir -p /mnt/data &&\
    mkdir -p /mnt/jobs &&\
    cd /usr/share/digits/digits &&\
    rm -rf jobs &&\
    ln -s /mnt/jobs .

VOLUME ["/mnt/data", "/mnt/jobs"]

EXPOSE 80

WORKDIR /usr/share/digits
ENTRYPOINT ["/usr/share/digits/digits-server"]
CMD ["--bind 0.0.0.0:80"]

