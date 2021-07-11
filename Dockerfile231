FROM ubuntu:16.04
MAINTAINER GoatWang

# ubuntu with python3.6 from https://github.com/miseyu/docker-ubuntu16-python3.6/blob/master/Dockerfile
RUN apt-get update && apt-get install -y software-properties-common && add-apt-repository ppa:deadsnakes/ppa && \
    apt-get update && apt-get install -y python3.6 python3.6-dev python3-pip
RUN ln -sfn /usr/bin/python3.6 /usr/bin/python3 && ln -sfn /usr/bin/python3 /usr/bin/python && ln -sfn /usr/bin/pip3 /usr/bin/pip
RUN apt-get install -y wget gcc g++ build-essential

# install gdal==2.3.1
RUN wget http://download.osgeo.org/gdal/2.3.1/gdal-2.3.1.tar.gz
RUN tar xzf gdal-2.3.1.tar.gz
WORKDIR gdal-2.3.1
RUN ./configure
RUN make
RUN make install
ENV LD_LIBRARY_PATH=/usr/local/lib:\$LD_LIBRARY_PATH
WORKDIR /

# install gdal-python
RUN pip3 install numpy==1.16.4
RUN pip3 install GDAL==$(gdalinfo --version | sed "s/GDAL //" | sed "s/, released [0-9][0-9][0-9][0-9]\/[0-9][0-9]\/[0-9][0-9]//")