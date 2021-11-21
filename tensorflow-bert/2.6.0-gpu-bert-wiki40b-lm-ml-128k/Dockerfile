FROM tensorflow/tensorflow:2.6.0-gpu

# andreclaudino/tensorflow-bert:2.6.0-gpu-bert-wiki40b-lm-ml-128k

LABEL maintainer "André Claudino <claudino@d2x.com.br>"
LABEL bert_model "wiki40b-lm-multilingual-128k"
LABEL bert_tfhub_url "https://tfhub.dev/google/wiki40b-lm-multilingual-128k/1"
LABEL model_path "/model-path"

RUN pip install tensorflow_text
ENV TFHUB_URL https://storage.googleapis.com/tfhub-modules/google/wiki40b-lm-multilingual-128k/1.tar.gz
ENV MODEL_PATH /model-path
RUN wget -c $TFHUB_URL -O - | tar -xz -C $MODEL_PATH