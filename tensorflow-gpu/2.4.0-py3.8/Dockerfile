FROM tensorflow/tensorflow:2.4.0-gpu

# andreclaudino/tensorflow-gpu:2.4.0-py3.8

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

USER root

## Install nvidia packages
ENV GET_PIP_FILE /tmp/get-pip.py
ENV PATH ${PATH}:/root/.local/bin

RUN apt install git python3.8 python3.8-distutils -y && \
    curl "https://bootstrap.pypa.io/get-pip.py" -o $GET_PIP_FILE && \
    python3.8 $GET_PIP_FILE && \
    rm $GET_PIP_FILE && \
    pip3.8 install --user tensorflow-gpu==2.4.0 && \
    apt-get purge --autoremove -y curl && \
    rm -rf /var/lib/apt/lists/*

RUN alias python3=python3.8 && \
    alias pip='python3.8 -m pip'