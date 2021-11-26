FROM tensorflow/tensorflow:2.5.2-gpu

# andreclaudino/tensorflow-autokeras:ak-1.0.16.post1-tf-2.5.0-gpu

LABEL maintainer "André Claudino <claudino@d2x.com.br>"
LABEL autokeras_version 1.0.16.post1
LABEL tensorflow_version 2.5.0-gpu

RUN pip3 install --upgrade pip
RUN alias python3=python3.8 && \
    alias pip='python3.8 -m pip'

RUN pip install autokeras==1.0.16.post1 \
                tensorflow-gpu==2.5.2 \
                tensorflow==2.5.2
