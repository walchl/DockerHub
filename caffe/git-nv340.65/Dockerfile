FROM walchl/cuda-6.5:340.65
MAINTAINER "Walter Chen-Hua Lu"
RUN apt-get update &&\
    apt-get -y install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libboost-all-dev libhdf5-serial-dev \
    libgflags-dev libgoogle-glog-dev liblmdb-dev protobuf-compiler \
    libatlas-base-dev \
    git bc vim &&\
    apt-get clean
RUN git clone https://github.com/BVLC/caffe.git ~/caffe
ADD cudnn-6.5-linux-R1.tgz /usr/local/
RUN ln -s /usr/local/cudnn-6.5-linux-R1/lib* /usr/local/lib/. &&\
    ln -s /usr/local/cudnn-6.5-linux-R1/*h /usr/local/include/. &&\
    ldconfig
RUN cd ~/caffe &&\
    cp Makefile.config.example Makefile.config &&\
    sed -i 's/^# USE_CUDNN/USE_CUDNN/' Makefile.config &&\
    make all ; make test
