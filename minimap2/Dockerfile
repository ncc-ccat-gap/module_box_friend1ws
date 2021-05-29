FROM ubuntu:20.04

MAINTAINER Yuichi Shiraishi <friend1ws@gmail.com>

RUN apt-get update && apt-get install -y \
    git \
    wget \
    bzip2 \
    make \
    gcc \
    zlib1g-dev \
    libbz2-dev \
    liblzma-dev \
    libcurl4-openssl-dev \
    libssl-dev \
    libncurses5-dev 

WORKDIR /usr/local

RUN wget https://github.com/lh3/minimap2/archive/refs/tags/v2.20.tar.gz && \
    tar zxvf v2.20.tar.gz && \
    cd minimap2-2.20 && \
    make

RUN wget https://github.com/samtools/samtools/releases/download/1.12/samtools-1.12.tar.bz2 && \
    tar jxvf samtools-1.12.tar.bz2 && \
    cd samtools-1.12 && \
    ./configure && make && make install

ENV PATH $PATH:/usr/local/minimap2-2.20
ENV PATH $PATH:/usr/local/samtools-1.12/bin


