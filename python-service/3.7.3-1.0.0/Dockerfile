FROM python:3.7.3-slim

# andreclaudino//python-service

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

RUN apt-get update && \
    apt-get install git -y && \
    rm -rf /var/lib/apt/lists

RUN pip3 install    newrelic==5.22.0.151 \
                    gunicorn==20.0.4