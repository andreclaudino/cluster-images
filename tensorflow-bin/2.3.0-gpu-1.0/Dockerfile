FROM ubuntu:focal AS downloader

# andreclaudino/tensorflow-bin:2.3.0-gpu-1.0

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

ENV TENSORFLOW_VERSION=2.3.0
ENV ACCELERATOR=gpu

RUN apt-get update && \
    apt-get install -y wget

RUN mkdir -p /downloader && \
    wget -c -O /downloader/lib-tensorflow.tar.gz \
        https://storage.googleapis.com/tensorflow/libtensorflow/libtensorflow-$ACCELERATOR-linux-x86_64-$TENSORFLOW_VERSION.tar.gz

RUN mkdir -p /downloader/libtensorflow/ && \
    tar -xzvf /downloader/lib-tensorflow.tar.gz -C /downloader/libtensorflow/

FROM tensorflow/tensorflow:2.3.0-gpu

WORKDIR /root/

COPY --from=downloader /downloader/libtensorflow/include/* /usr/include/
COPY --from=downloader /downloader/libtensorflow/lib/* /usr/lib/

RUN ln /usr/lib/libtensorflow.so /usr/lib/libtensorflow.so.1

ENV LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib/
