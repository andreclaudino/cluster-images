FROM tensorflow/tensorflow:2.7.0

# andreclaudino/tensorflow-bert:2.7.0-small-bert_en_uncased_L-2_H-128_A-2

LABEL maintainer "André Claudino <claudino@d2x.com.br>"
LABEL bert_model "2.7.0-small-bert_en_uncased_L-2_H-128_A-2"
LABEL bert_tfhub_url "https://tfhub.dev/tensorflow/small_bert/bert_en_uncased_L-2_H-128_A-2/2"
LABEL model_path "/resources/encoder-model-path"

RUN pip install tensorflow_text

RUN apt-get update && \
		apt-get install wget && \
		apt-get clean autoclean && \
		apt-get autoremove --yes

ENV TFHUB_PREPROCESSOR_URL=https://storage.googleapis.com/tfhub-modules/tensorflow/bert_en_uncased_preprocess/3.tar.gz
ENV PROCESSOR_MODEL_PATH=/resources/processor-model-path
RUN mkdir -p $PROCESSOR_MODEL_PATH && \
		wget -c $TFHUB_PREPROCESSOR_URL -O - | tar -xz -C $PROCESSOR_MODEL_PATH

ENV TFHUB_ENCODER_URL=https://storage.googleapis.com/tfhub-modules/tensorflow/small_bert/bert_en_uncased_L-2_H-128_A-2/2.tar.gz
ENV ENCODER_MODEL_PATH=/resources/encoder-model-path
RUN mkdir -p $ENCODER_MODEL_PATH && \
		wget -c $TFHUB_ENCODER_URL -O - | tar -xz -C $ENCODER_MODEL_PATH
