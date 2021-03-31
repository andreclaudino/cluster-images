FROM tensorflow/tensorflow:2.3.1-gpu

# andreclaudino/tensorflow-gpu:2.1.0-py3.7v2

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

USER root

## Install nvidia packages
ENV GET_PIP_FILE /tmp/get-pip.py

RUN apt install git python3.7 python3.7-distutils -y && \
    curl "https://bootstrap.pypa.io/get-pip.py" -o $GET_PIP_FILE && \
    python3.7 $GET_PIP_FILE && \
    rm $GET_PIP_FILE && \
    pip3.7 install --user tensorflow-gpu==2.1.0 && \
    apt-get purge --autoremove -y curl && \
    rm -rf /var/lib/apt/lists/*

RUN alias python3=python3.7 && \
    alias pip='python3.7 -m pip' && \
    alias pip='python3.7 -m pip'