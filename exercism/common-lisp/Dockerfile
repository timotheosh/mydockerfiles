FROM ubuntu:18.04
RUN apt-get update && apt-get -y install build-essential gcc git make autoconf automake libcurl4-openssl-dev libz-dev
RUN cd /usr/local/src/ && \
    git clone https://github.com/roswell/roswell.git && \
    cd roswell && \
    git checkout v20.01.14.104 && \
    ./bootstrap && \
    ./configure && \
    make && \
    make install && \
    cd .. && \
    rm -rf roswell
RUN useradd -s /bin/bash -m roswell
USER roswell
WORKDIR /home/roswell
RUN ros init
RUN ros install sbcl/2.0.1
RUN ros install lisp-unit lisp-unit2 rove cl-ppcre
